# taxon-utils之寻找共同祖先：lca

### 一、taxon-utils lca介绍

**功能描述：**

`taxon-utils lca` 对提供的多个节点，从物种树中寻找共同祖先，输出对应的共同祖先节点

**命令行接口：**

    $ taxon-utils lca
    
    Usage: taxon-utils lca <taxon.map> <match>


### 二、使用场景实例及其用法

**示例演示：**

示例文件在: `data` 目录

**示例文件：**  `taxon.map.gz`

    $ zcat taxon.map.gz | head -n 6


    1       1       no rank root    root
    2       1       superkingdom    Archaea root
    3       1       superkingdom    Bacteria        root
    4       3       phylum  4572-55 Bacteria
    5       3       phylum  AABM5-125-24    Bacteria
    6       3       phylum  AB1-6   Bacteria

**运行命令 :**

    $ cat reads.txt


    A01050:204:HF7FGDSXY:4:1104:4580:31876  21349
    A01050:204:HF7FGDSXY:4:1104:4580:31876  21349
    A01050:204:HF7FGDSXY:4:1104:4580:31876  21353
    A01050:204:HF7FGDSXY:4:1104:4580:31876  21350


`注意事项`: 输入文件，2列，第一列为标识符， 第二为物种分类编号；


    $ taxon-utils  lca taxon.map.gz  reads.txt


    A01050:204:HF7FGDSXY:4:1104:4580:31876  4       7115


`注意事项`: 输出文件，3列，第一列为标识符，第二列为LCA前同一标识符分类的分类个数， 第三为`LCA`后物种分类编号；

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-08-10 11:56 AM
