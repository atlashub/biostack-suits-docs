# atlas-utils之获取对应的列：subsamples

### 一、atlas-utils subsamples介绍

**功能描述：**

`atlas-utils subsamples` 根据指定的列标识符（第一行中指定的名称），获取对应的列或者多列信息，强制包含第一列信息，比如从 **(Z)OTU** 表中抽取一部分样本的数值，形成新的 **(Z)OTU** 表；。

**命令行接口：**

    $ atlas-utils subsamples
    
    Usage: atlas-utils subsamples <otu-table>  <samples| ',' >

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

获取指定`A-1`列的信息。

    $ atlas-utils subsamples zotu_table.txt A-1 | head


    #OTU ID A-1
    ZOTU_1  0
    ZOTU_2  223
    ZOTU_3  0
    ZOTU_4  0
    ZOTU_5  0
    ZOTU_6  1
    ZOTU_7  0
    ZOTU_8  0
    ZOTU_9  0


获取多列的信息


    $ atlas-utils subsamples zotu_table.txt A-1,B-1 | head


    #OTU ID A-1     B-1
    ZOTU_1  0       87
    ZOTU_2  223     1268
    ZOTU_3  0       162
    ZOTU_4  0       99
    ZOTU_5  0       1
    ZOTU_6  1       9
    ZOTU_7  0       73
    ZOTU_8  0       1353
    ZOTU_9  0       1172

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-08-10 11:56 AM

