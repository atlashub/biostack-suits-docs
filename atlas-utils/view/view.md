# atlas-utils之简单处理表格行操作：view

### 一、atlas-utils view介绍

**功能描述：**

`atlas-utils view` 简单处理表格行操作，比如添加注释符号（#），忽略注释符号以及空行。

**命令行接口：**

    $ atlas-utils view
    
    Usage: atlas-utils view <tsv>
    
    Options:
       -c   Add comment char '#' to the first line.
       -b   Remove the blank lines.

**可选参数：**

     -c  在第一行添加'#';
     -b  删除空白行

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**`quant.sf`


    $ cat  quant.sf | head -n 7


    Name    Length  EffectiveLength TPM     NumReads
    TrA0001W        9003    8740.853        0.048685        1.000
    TrA0002C        2364    2101.853        0.202465        1.000
    TrA0003W        1065    802.853 0.000000        0.000
    TrA0004W        783     521.202 0.000000        0.000
    TrA0005W        654     392.544 0.000000        0.000
    TrA0006W        921     658.964 0.000000        0.000


**运行命令：**

使用参数`-c`，在第一行添加'#'。


    $ atlas-utils view -c quant.sf | head


    #Name   Length  EffectiveLength TPM     NumReads
    TrA0001W        9003    8740.853        0.048685        1.000
    TrA0002C        2364    2101.853        0.202465        1.000
    TrA0003W        1065    802.853 0.000000        0.000
    TrA0004W        783     521.202 0.000000        0.000
    TrA0005W        654     392.544 0.000000        0.000
    TrA0006W        921     658.964 0.000000        0.000
    TrA0007W        927     664.957 12.799413       20.000
    TrA0008W        1032    769.853 4.974941        9.000
    TrA0009W        768     506.243 1.681218        2.000    


**参数选项1：** 设置 `-b` 参数，合并多个注释文件,删除中间的注释行.

示例文件: `alpha.A-1.txt, alpha.A-2.txt` alpha多样性计算文件

    $ cat  alpha.A-1.txt | cut -f1,2,4


    #Sample berger_parker   chao1
    A-1     0.0313  433.2


    $ cat  alpha.A-2.txt  alpha.A-1.txt | atlas-utils view -b - | cut -f1,2,3


    #Sample berger_parker   buzas_gibson
    A-2     0.0356  0.00743
    A-1     0.0313  0.00669

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

