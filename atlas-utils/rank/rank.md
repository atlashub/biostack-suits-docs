# atlas-utils之对(Z)OTU排序：rank

### 一、atlas-utils rank介绍

**功能描述：**

`atlas-utils rank` 对给定**(Z)OTU**表进行排序，并输出指定数据的 **(Z)OTU** 或者物种分类，其余可归并到`Others`分类。

**命令行接口：**

    $ atlas-utils rank
    
    Usage: tsv-utils rank [options] <tsv>
    
    Options: 
    -r  INT top catalogs.
    -m      merge remain to others level.
    -a      merge above_ to others level.

**可选参数：**

    -r  整数 显示指定的行数;
    -m       合并剩下的行到一起;
    -a       将above_level的分类合并至Others分类;

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**`zotu_table.txt`

    $ cat zotu_table.txt | head -n 10


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

对`zotu_table.txt`进行排序。

    $ atlas-utils rank  zotu_table.txt | head -n 10


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_6  1       2       9       16      1155    1938
    ZOTU_7  0       0       73      41      1044    1883
    ZOTU_10 0       0       0       0       889     1650
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_13 0       0       1       0       795     1513


**参数选项1：** 设置 ` -r` 参数，指定显示的行数。

    $ atlas-utils rank -r 10 zotu_table.txt


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_6  1       2       9       16      1155    1938
    ZOTU_7  0       0       73      41      1044    1883
    ZOTU_10 0       0       0       0       889     1650
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_13 0       0       1       0       795     1513
    ZOTU_12 0       0       1       0       886     1503


**参数选项2：** 设置 ` -m` 参数，将剩余的合并在一起。


    $ atlas-utils rank -r 10 -m zotu_table.txt


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_6  1       2       9       16      1155    1938
    ZOTU_7  0       0       73      41      1044    1883
    ZOTU_10 0       0       0       0       889     1650
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_13 0       0       1       0       795     1513
    Others  2.728e+04       2.391e+04       1.71e+04        1.579e+04       9850    1.643e+04


`注意事项`: 针对 above_`level` level为分类水平, 是指那些可以至少分类到 `kindom`水平, 但是又高于当前分类水平的分类, 此类在执行`rank -a` 操作会被归并到`Others`分类。


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

