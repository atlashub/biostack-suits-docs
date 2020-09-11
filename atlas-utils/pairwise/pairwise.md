# atlas-utils之 ZOTU 表格式转换：pairwise

### 一、atlas-utils pairwise介绍

**功能描述：**

`atlas-utils pairwise` 将常规OTU表转换成, `样本\t数值\tZOTU号`三列文件格式。

**命令行接口：**

    $ atlas-utils pairwise
    
    Usage: atlas-utils pairwise <otutab>


### 二、使用场景实例及其用法

**使用场景经典案例：**

适用于`phylocom`的输入格式。

**示例演示：**

**示例文件：**`zotu_table.txt`


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


**运行命令：** 将常规`OTU`表转换成, `样本\t数值\tZOTU号`三列文件格式


    $ atlas-utils pairwise zotu_table.txt | head


    A-1     0       ZOTU_1
    A-2     0       ZOTU_1
    B-1     87      ZOTU_1
    B-2     278     ZOTU_1
    C-1     1829    ZOTU_1
    C-2     3608    ZOTU_1
    A-1     223     ZOTU_2
    A-2     447     ZOTU_2
    B-1     1268    ZOTU_2
    B-2     1583    ZOTU_2

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM