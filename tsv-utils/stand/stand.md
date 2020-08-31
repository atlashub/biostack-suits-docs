# tsv-utils之数值型制表符文件标准化:  stand

### 一、tsv-utils stand 介绍

**功能描述：**

`tsv-utils stand`  对数值型制表符文件标准化，将数值标准化一个固定的数值，比如：`OTU表`，或者 宏基因组丰度数值表； 按照公式：
$$
z =  \dfrac {x - \mu}{\sigma}
$$

进行标准化。

**命令行接口**：

    $ tsv-utils stand
    
    Usage: tsv-utils  stand <tsv>

### 二、使用场景实例及其用法

**示例演示**

**示例文件**：`zotu_table.txt`。


    $ cat  zotu_table.txt | head -n 6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143


**运行命令：**, 对OTU表进行标准化操作


    $ tsv-utils stand zotu_table.txt | head -n 6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  -1.072664       -1.056552       1.763399        2.448481        4.125404        3.969483
    ZOTU_2  1.717391        2.179687        3.249778        3.427962        1.923473        1.778275
    ZOTU_3  -1.072664       -1.056552       2.106728        2.134844        3.818489        3.647504
    ZOTU_4  -1.072664       -1.056552       1.834600        1.489932        3.888925        3.687531
    ZOTU_5  -1.072664       -1.056552       -0.344312       0.511520        3.871795        3.680064



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 9:03:47 PM



