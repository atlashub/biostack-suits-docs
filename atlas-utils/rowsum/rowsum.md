# atlas-utils之计算ZOTU表中的每个ZOTU的Tags数：rowsum

### 一、atlas-utils rowsum介绍

**功能描述：**

`atlas-utils rowsum` 计算ZOTU表中的每个ZOTU的Tags数， 可以结合`tsv-utils stats`进行统计。

**命令行接口：**

    $ atlas-utils rowsum
    
    Usage: atlas-utils rowsum <otutab>

### 二、使用场景实例及其用法

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


**运行命令：**

计算`ZOTU`表中的每个`ZOTU`的`Tags`数


    $ atlas-utils rowsum zotu_table.txt | head


    #otu    value
    ZOTU_1  5802
    ZOTU_2  3642
    ZOTU_3  3458
    ZOTU_4  3571
    ZOTU_5  3368
    ZOTU_6  3121
    ZOTU_7  3041
    ZOTU_8  2587
    ZOTU_9  2197

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。



Last Update: 2020-09-09 11:56 AM