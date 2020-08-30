# tsv-utils之抽取或者删除指定列：cut


### 一、tsv-utils cut 介绍

**功能描述：**

`tsv-utils cut` 根据指定的列数值抽取或者删除对应的列，抽取列按照指定顺序重新组合。

**命令行接口：**

    $ tsv-utils  cut
    
    Usage: tsv-utils cut [options]
    Options:
      -f  STR  field to split
      -s  STR  sperator, default: [\t]
      -d       delete mode.

**可选参数：**

    -f  指定  抽取的列
    -s  指定  分隔符， 默认"\t"
    -d        删除指定的行



### 二、使用场景实例及其用法

**示例演示**示例

**示例文件：** `zotu_table.txt, zotu_table.csv`

    $ cat zotu_table.txt | head -n 6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143


    $ cat zotu_table.csv | head -n 6


    #OTU ID,A-1,A-2,B-1,B-2,C-1,C-2
    ZOTU_1,0,0,87,278,1829,3608
    ZOTU_2,223,447,1268,1583,52,69
    ZOTU_3,0,0,162,159,1116,2021
    ZOTU_4,0,0,99,50,1250,2172
    ZOTU_5,0,0,1,8,1216,2143


**运行命令：**

**选项参数1**: 使用 `-f` 指定选取的列, 多列使用`,`分割。

    $ tsv-utils cut -f 1,2,3  zotu_table.txt  | head -n6


    #OTU ID A-1     A-2
    ZOTU_1  0       0
    ZOTU_2  223     447
    ZOTU_3  0       0
    ZOTU_4  0       0
    ZOTU_5  0       0


**选项参数2**: 通过设置 `-s` 以逗号作为列之间的分隔符。

    $ tsv-utils cut -s','  -f 1,2,3  zotu_table.csv  | head -n6


    #OTU ID,A-1,A-2
    ZOTU_1,0,0
    ZOTU_2,223,447
    ZOTU_3,0,0
    ZOTU_4,0,0
    ZOTU_5,0,0


`注意事项`: `-f` 指定的列具有顺序性。


**选项参数3：** 设置`-d`参数，删除 `zotu_table.txt` 中指定的列数据

    $ tsv-utils  cut -d -f2,3  zotu_table.txt  | head


    #OTU ID B-1     B-2     C-1     C-2
    ZOTU_1  87      278     1829    3608
    ZOTU_2  1268    1583    52      69
    ZOTU_3  162     159     1116    2021
    ZOTU_4  99      50      1250    2172
    ZOTU_5  1       8       1216    2143
    ZOTU_6  9       16      1155    1938
    ZOTU_7  73      41      1044    1883
    ZOTU_8  1353    1231    2       1
    ZOTU_9  1172    1022    1       2


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 3:38:56 PM
