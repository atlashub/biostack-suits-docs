# tsv-utils之矩格式转换: matrix2melt

### 一、tsv-utils matrix2melt 介绍

**功能描述：**

`tsv-utils matrix2melt` 根据提供的`ID`映射表抽取矩阵中的数值，可用于估计分组中的`ID`之间的距离，比如Anosim作图；

**命令行接口：**

    $ tsv-utils  matrix2melt

    Usage: tsv-utils matrix2melt <matrix> <map>


### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**  `bray_curtis.txt`，`mapping_file.txt`


    $ cat bray_curtis.txt


    bray_curtis     A-1     A-2     B-1     B-2     C-1     C-2
    A-1     0       0.110   0.986   0.986   0.990   0.991
    A-2     0.110   0       0.976   0.976   0.990   0.990
    B-1     0.986   0.976   0       0.134   0.872   0.874
    B-2     0.986   0.976   0.134   0       0.868   0.870
    C-1     0.990   0.990   0.872   0.868   0       0.0601
    C-2     0.991   0.990   0.874   0.870   0.0601  0


    $ cat mapping_file.txt | head -n6


    #SampleID       Description
    A-1     A
    A-2     A
    B-1     B
    B-2     B
    C-1     C


**运行命令：**


    $ tsv-utils matrix2melt  bray_curtis.txt  mapping_file.txt


    A       0.110
    B       0.134
    C       0.0601


本文材料为 **BASE** (Biostack Applied bioinformatic SEies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/31/2020 8:52:04 PM
