# tsv-utils之获取子矩阵:submatrix

### 一、tsv-utils submatrix介绍

**功能描述：**

`tsv-utils submatrix` 针对矩阵（方阵）进行抽取子阵。

**命令行接口：**

    $ tsv-utils submatrix
    
    Usage:tsv-utils submatrix  [options]  <matrix> <samples>
    
    Options:
      -d    Export distance matrix format.

**可选参数：**

```
 -d		删除第一行第一列的表头
```



### 二、使用场景实例及其用法

**经典使用场景：**

1. 16S扩增子数据分析，对大样本距离矩阵拆分出小的距离矩阵。


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


    $ cat list
    A-1
    A-2
    B-1
    B-2


**运行命令：**

    $ tsv-utils  submatrix  bray_curtis.txt  list


    bray_curtis     A-1     A-2     B-1     B-2
    A-1     0       0.110   0.986   0.986
    A-2     0.110   0       0.976   0.976
    B-1     0.986   0.976   0       0.134
    B-2     0.986   0.976   0.134   0

**参数使用1：**使用 `-d` 参数, 可以去除`bray_curtis` 字符串

    $ tsv-utils  submatrix -d  bray_curtis.txt  list
            A-1     A-2     B-1     B-2
    A-1     0       0.110   0.986   0.986
    A-2     0.110   0       0.976   0.976
    B-1     0.986   0.976   0       0.134
    B-2     0.986   0.976   0.134   0



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-08-10 11:56 AM