# atlas-utils之根据指定样本大小无放回式抽样：rare

### 一、atlas-utils rare介绍

**功能描述：**

`atlas-utils rare` 根据指定样本大小对OTU表进行无放回式抽样, 进行抽平操作, 一般使用所有样本中的`Tags`数的最小值。

**命令行接口：**

    $ atlas-utils rare
    
    Usage: atlas-utils rare [-s seed=11] <otutab> <sample_size>
    
    Options: 
     -s INT    RNG seed [11]

**可选参数：**

      -s  整型   保证可以重复， 设置SEED值；


### 二、使用场景实例及其用法

**使用场景经典案例：**

扩增子数据分析： 抽平操作

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

确定抽平的样本大小


    $ atlas-utils  min_size zotu_table.txt


    17926


指定样本大小为`17926`对`ZOTU`表进行无放回式抽样, 进行抽平操作


    $ atlas-utils rare -s 11 zotu_table.txt 17926 | head -n 10


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  1       1       82      277     1717    1933
    ZOTU_2  135     324     1216    1583    51      34
    ZOTU_3  0       0       152     159     1018    1095
    ZOTU_4  0       0       96      50      1156    1155
    ZOTU_5  0       0       1       8       1122    1125
    ZOTU_6  0       0       9       16      1080    1040
    ZOTU_7  0       0       71      41      967     1019
    ZOTU_8  0       0       1287    1231    2       0
    ZOTU_9  0       0       1112    1022    1       0


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-11 11:56 AM