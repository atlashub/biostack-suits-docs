# tsv-utils之对文件添加分组表头：groupline

### 一、tsv-utils groupline  介绍

**功能描述：**

`tsv-utils groupline`  根据`key/value`对注释文件添加分组表头。

**命令行接口**：

    $ tsv-utils groupline
    
    Usage: tsv-utils groupline [options] <db> <text>
    
    Options: -r  replace headline [default: add headline].

**可选参数：**

    -r      添加该参数可以将表头替换，默认为添加表头；


### 二、使用场景实例及其用法

**示例演示**

**示例文件：** `genus.freqs.txt, mapping_file.txt`


    $ cat  genus.freqs.txt | head -n 6


    #level  A-1     A-2     B-1     B-2     C-1     C-2
    Parvibaculum    0.0003635       0.0002874       5.318e-05       0       0.004845        0.004368
    Agromyces       0       0       0       0       0.009585        0.0114
    Pigmentiphaga   0.000109        0.0001642       0.002765        0.001841        5.209e-05       0
    Mangrovibacterium       0       0       0.002499        0.001785        0       0
    Pseudonocardia  0.00189 0.001683        0       0       0       0


    $ cat mapping_file.txt


    #SampleID       Description
    A-1     A
    A-2     A
    B-1     B
    B-2     B
    C-1     C
    C-2     C

**运行命令：** 默认参数

    $ tsv-utils  groupline  mapping_file.txt  genus.freqs.txt | head -n 6


    #group  A       A       B       B       C       C
    #level  A-1     A-2     B-1     B-2     C-1     C-2
    Parvibaculum    0.0003635       0.0002874       5.318e-05       0       0.004845        0.004368
    Agromyces       0       0       0       0       0.009585        0.0114
    Pigmentiphaga   0.000109        0.0001642       0.002765        0.001841        5.209e-05       0
    Mangrovibacterium       0       0       0.002499        0.001785        0       0


**参数示例:** 使用 `-r` 删除掉样本名称

    $ tsv-utils  groupline  -r  mapping_file.txt  genus.freqs.txt | head -n 6


    #group  A       A       B       B       C       C
    Parvibaculum    0.0003635       0.0002874       5.318e-05       0       0.004845        0.004368
    Agromyces       0       0       0       0       0.009585        0.0114
    Pigmentiphaga   0.000109        0.0001642       0.002765        0.001841        5.209e-05       0
    Mangrovibacterium       0       0       0.002499        0.001785        0       0
    Pseudonocardia  0.00189 0.001683        0       0       0       0



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 7:21:56 PM
