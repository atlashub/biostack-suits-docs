# tsv-utils  之计算相对丰度：abundance

### 一、tsv-utils  abundance 介绍

**功能描述：**

`tsv-utils abundance` 通过输入数值型制表符文件计算相对丰度。

**命令行接口：**

    $ tsv-utils abundance
    
    Usage: tsv-utils abundance <tsv>
    

### 二、使用场景实例及其用法

**使用场景经典案例：**

1. 扩增子数据分析，比如`16S`微生物多样性根据 `ZOTU` 的数值表，计算 `ZOTU` 的相对丰度。

**示例演示：**

示例文件：`zotu_table.txt` 

    $ cat zotu_table.txt |head
    
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

运行命令：

    $ tsv-utils abundance zotu_table.txt | head
    
    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       0.4627  1.551   9.528   10.79
    ZOTU_2  0.8106  1.835   6.743   8.831   0.2709  0.2064
    ZOTU_3  0       0       0.8615  0.887   5.814   6.045
    ZOTU_4  0       0       0.5265  0.2789  6.512   6.497
    ZOTU_5  0       0       0.005318        0.04463 6.335   6.41
    ZOTU_6  0.003635        0.008211        0.04786 0.08926 6.017   5.797
    ZOTU_7  0       0       0.3882  0.2287  5.439   5.633
    ZOTU_8  0       0       7.195   6.867   0.01042 0.002991
    ZOTU_9  0       0       6.233   5.701   0.005209        0.005983

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有.


Last Update: Friday, August 28, 2020