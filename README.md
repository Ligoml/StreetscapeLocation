# StreetscapeLocation
“交通银行杯”第六届中国研究生智慧城市技术与创意设计大赛

- [x] 纠正图像 主要代码distort.py  
[参考](https://blog.csdn.net/hpuhjl/article/details/80899931)  

- [x] 图像搜索   
[参考](https://github.com/zibuyu1995/ApplicationInImageProcessing/tree/master/orb_image_search)

- [ ] 确定大概定位（初赛阶段）   

- [ ] 双目视觉配准PCL[参考](https://www.cnblogs.com/riddick/p/8486223.html)   

- [ ] 点云匹配准确定位（复赛）[参考](https://blog.csdn.net/wishchin/article/details/74279021)  



### 算法包操作流程：
- 数据集准备，请将数据集按照不同的scene解压缩，并存放于同一个文件夹下：
.. code-block:: none
    
    smart_city/ \
    |---scene1_jiading_lib_training/ \
    |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---PIC_20190522_100025/ \
    |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---PIC_20190522_100255/ \
    |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---.../ \
    |&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---scene1_jiading_lib_training_coordinates.csv \
    |---scene1_jiading_lib_test/ \
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---PIC_20190522_100509/ \
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---PIC_20190522_100546/ \
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|---.../

  注：scene4的training坐标文件编码格式有问题，请更正后执行后续操作，否则会报UnicodeDecodeError

- 进入算法包 cd upload_code 在terminal中运行main.py:
    
    python main.py \
    --root path/to/smart_city-data \
    --example-result ../example_result.csv \
    --save-dir save_file/ \
    --result-file result.csv 
    
  注：root传入数据集所在的地址，建议添加绝对路径；example_result传入组委会给定的example_result.csv文件用于校验最终的输出文件格式；save_dir定义中间文件的存储路径；result_file定义最终结果文件的存储路径。root和example_result是必须传入的参数，save_dir和result_file有默认值，可不设置。
  
- 获得结果文件result.csv，您可在设置的路径找到文件，或在main.py同一级目录下找到文件。
