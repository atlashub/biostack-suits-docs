# tsv-utils之数值型制表符文件标准化: norm

### 一、tsv-utils norm 介绍

**功能描述：**

`tsv-utils norm`  对数值型制表符文件标准化，将数值标准化一个固定的数值，比如：`ZOTU表`，或者 宏基因组丰度数值表； 按照公式：

$$
new =  \dfrac {old * factor}{total}
$$

进行标准化。

**命令行接口**：

    $ tsv-utils  norm
    
    Usage: tsv-utils norm  [options] <tsv> <factor: 30000>
    
    Options:
       -r   Round value to Int.

**可选参数：**

    -r  将数值变为整数;


### 二、使用场景实例及其用法

**示例演示**

**示例文件**：`zotu_table.txt`

    $ cat zotu_table.txt | head -n6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143


**运行命令：** 对`ZOTU`表进行标准化操作

    $ tsv-utils norm zotu_table.txt 30000 | head -n 6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0.000000        0.000000        138.800255      465.246011      2858.408002     3237.810350
    ZOTU_2  243.193137      550.515210      2022.973835     2649.224590     81.266931       61.920431
    ZOTU_3  0.000000        0.000000        258.455648      266.093942      1744.113357     1813.640443
    ZOTU_4  0.000000        0.000000        157.945118      83.677340       1953.531986     1949.147472
    ZOTU_5  0.000000        0.000000        1.595405        13.388374       1900.395916     1923.122943


`参数示例1:` 添加列号。

    $ tsv-utils norm -r zotu_table.txt 30000 | head -n 6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       139     465     2858    3238
    ZOTU_2  243     551     2023    2649    81      62
    ZOTU_3  0       0       258     266     1744    1814
    ZOTU_4  0       0       158     84      1954    1949
    ZOTU_5  0       0       2       13      1900    1923


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 10:36:19 PM


