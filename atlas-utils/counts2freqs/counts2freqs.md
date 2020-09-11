# atlas-utils之将**(Z)OTU**表的**counts** 转换成相对丰度表：counts2freqs

### 一、atlas-utils counts2freqs介绍

**功能描述：**

`atlas-utils counts2freqs` 将 **(Z)OTU** 表的 **counts**  转换成相对丰度表。

**命令行接口：**

    $ atlas-utils counts2freqs
    
    Usage:  atlas-utils counts2freqs  <counts.table>


### 二、使用场景实例及其用法

**示例演示：**

**示例文件：** `zotu_table.txt`

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

**运行命令：** 给定 `zotu_table.txt` 中的 `counts` 转换成相对丰度表。

    $ atlas-utils counts2freqs zotu_table.txt | head


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       0.004627        0.01551 0.09528 0.1079
    ZOTU_2  0.008106        0.01835 0.06743 0.08831 0.002709        0.002064
    ZOTU_3  0       0       0.008615        0.00887 0.05814 0.06045
    ZOTU_4  0       0       0.005265        0.002789        0.06512 0.06497
    ZOTU_5  0       0       5.318e-05       0.0004463       0.06335 0.0641
    ZOTU_6  3.635e-05       8.211e-05       0.0004786       0.0008926       0.06017 0.05797
    ZOTU_7  0       0       0.003882        0.002287        0.05439 0.05633
    ZOTU_8  0       0       0.07195 0.06867 0.0001042       2.991e-05
    ZOTU_9  0       0       0.06233 0.05701 5.209e-05       5.983e-05


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

