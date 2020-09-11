# atlas-utils之对ZOTU表进行按照样本数目进行分割：partition

### 一、atlas-utils partition介绍

**功能描述：**

`atlas-utils partition` 根据样本编号对`ZOTU`表进行拆分，返回分割的样本数目。

**命令行接口：**

    $ atlas-utils partition
    
    Usage: atlas-utils partition [options] <otutab> <prefix>
    
    Options:
      -n  samples per partition: default: [30];


**可选参数：**

      -n   每个样品的大小，默认为30；

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**


    $ cat zotu_table.txt | head


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143
    ZOTU_6  1       2       9       16      1155    1938
    ZOTU_7  0       0       73      41      1044    1883
    ZOTU_8  0       0       1353    1231    2       1
    ZOTU_9  0       0       1172    1022    1       2

**运行命令：**

将`zotu`表按样本编号切割，指定参数`-n`为`2`，每两个样本一个文件


    $ ls 


    zotu_table.txt


    $ atlas-utils partition -n 2 zotu_table.txt sample


    3


    $ ls


    sample.1.txt  sample.2.txt  sample.3.txt  zotu_table.txt

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-11 11:56 AM