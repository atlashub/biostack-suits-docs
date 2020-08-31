# tsv-utils之指定的文件列进行重新排序: reorder

### 一、tsv-utils reorder 介绍

**功能描述：**

`tsv-utils reorder` 根据列表的顺序，调整指定文件的顺序。

**命令行接口：**

    $ tsv-utils  reorder
    
    Usage: tsv-utils reorder [options] <tsv> <list>
    
    Options:
      -t INT Target in fields to reorder, default: [1]


**可选参数：**

    -t  整数      指定矩阵中需要排序的列，默认为第一列；

### 二、使用场景实例及其用法

**示例演示:**

**示例文件**：`alpha.txt, list`。

    $ cat alpha.txt | cut -f1,2,3


    #Sample berger_parker   buzas_gibson
    A-2     0.0356  0.00743
    A-1     0.0313  0.00669
    B-1     0.072   0.00502

```
$ cat list
```


    A-1
    A-2
    B-2

**运行命令**

    $ tsv-utils  reorder  -t 1  alpha.txt  list | cut -f1,2,3
    
    #Sample berger_parker   buzas_gibson
    A-1     0.0313  0.00669
    A-2     0.0356  0.00743

`注意事项`: 最后的输出结果值包含列表中包含的行, 如文件中不存在该列表的行,自动忽略.

本材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有.

Last Update: Saturday, August 29, 2020