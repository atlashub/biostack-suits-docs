# tsv-utils之转置矩阵:  transpose

### 一、tsv-utils transpose介绍

**功能描述：**

`tsv-utils transpose` 对矩阵文件转置操作。

**命令行接口：**

    $ tsv-utils transpose


    Usage: tsv-utils transpose <tsv>

### 二、使用场景实例及其用法

**示例演示**

示例文件：`zotu_table.txt`


    $ cat zotu_table.txt | head -n6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143

**运行命令：**

    $ tsv-utils  transpose zotu_table.txt  | cut -f1,2,3 | head -n 6
    
    #OTU ID ZOTU_1  ZOTU_2
    A-1     0       223
    A-2     0       447
    B-1     87      1268
    B-2     278     1583
    C-1     1829    52


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: Saturday, August 29, 2020
