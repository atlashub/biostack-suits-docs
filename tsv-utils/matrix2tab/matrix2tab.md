# tsv-utils之矩格式转换: matrix2tab

### 一、tsv-utils matrix2tab 介绍

**功能描述：**

`tsv-utils matrix2tab` 将矩阵格式文件转换成制表符分割文件;

    	A	B
    A	0	2
    B	2	0

另一种转换成下面类`邻接表`格式：

    A   A   0
    A   B   2


**命令行接口：**
    
    $ tsv-utils matrix2tab
    
    Usage: tsv-utils matrix2tab <matrix>

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**  `bray_curtis.txt`，`list`


    $ cat bray_curtis.txt


    bray_curtis     A-1     A-2     B-1     B-2     C-1     C-2
    A-1     0       0.110   0.986   0.986   0.990   0.991
    A-2     0.110   0       0.976   0.976   0.990   0.990
    B-1     0.986   0.976   0       0.134   0.872   0.874
    B-2     0.986   0.976   0.134   0       0.868   0.870
    C-1     0.990   0.990   0.872   0.868   0       0.0601
    C-2     0.991   0.990   0.874   0.870   0.0601  0

**运行命令：**

    $ tsv-utils matrix2tab bray_curtis.txt | head -n6


    A-1     A-2     0.110
    A-1     B-1     0.986
    A-1     B-2     0.986
    A-1     C-1     0.990
    A-1     C-2     0.991
    A-2     B-1     0.976



本文材料为 **BASE** (Biostack Applied bioinformatic SEies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2018-05-24 5:21 PM
