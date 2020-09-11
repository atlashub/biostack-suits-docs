# atlas-utils之构建**Unique**序列丰度表：unique_table

### 一、atlas-utils barcode介绍

**功能描述：**

`atlas-utils unique_table` 使用**USEATCH unique**子命令构建**Unique**序列丰度表。

**命令行接口：**

    $ atlas-utils unique_table
    
    Usage: atlas-utils uniques_table  <mapping_file> <maps>

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**`mapping_file.txt`，`A-1.map.txt`

    $ cat mapping_file.txt


    #SampleID       Description
    A-1     A
    A-2     A
    B-1     B
    B-2     B
    C-1     C
    C-2     C


    $ cat A-1.map.txt | head


    A-1_36;sample=A-1;      ZOTU_464
    A-1_34;sample=A-1;      ZOTU_38
    A-1_66;sample=A-1;      ZOTU_42
    A-1_15;sample=A-1;      ZOTU_42
    A-1_41;sample=A-1;      ZOTU_113
    A-1_67;sample=A-1;      ZOTU_45
    A-1_48;sample=A-1;      ZOTU_554
    A-1_45;sample=A-1;      ZOTU_391
    A-1_68;sample=A-1;      ZOTU_16
    A-1_60;sample=A-1;      ZOTU_236

**运行命令：**

构建**Unique**序列丰度表。

    $ atlas-utils unique_table mapping_file.txt  A-1.map.txt | head


    #OTU table      A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_464        24      0       0       0       0       0
    ZOTU_38 346     0       0       0       0       0
    ZOTU_42 310     0       0       0       0       0
    ZOTU_113        136     0       0       0       0       0
    ZOTU_45 296     0       0       0       0       0
    ZOTU_554        27      0       0       0       0       0
    ZOTU_391        28      0       0       0       0       0
    ZOTU_16 860     0       0       0       0       0
    ZOTU_236        63      0       0       0       0       0

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

