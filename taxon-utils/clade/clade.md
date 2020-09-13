# taxon-utils之输给定节点下的所有子节点：clade

### 一、taxon-utils clade介绍

**功能描述：**

`taxon-utils clade` 提供一个节点，返回该节点在树中的所有子节点， 比如获得所有属于病毒分类的所有的`ID`

**命令行接口：**

    $ taxon-utils clade
    
    Usage: taxon-utils  clade  <taxon.map>  <clade: NCBI Taxonomy ID, ie: 10239(viruses)>


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

输出所有属于`Lactobacillus: 7115` 下面所有的分类。

    $ taxon-utils  clade  taxon.map.gz  7115 | taxon-utils translate -c 1  taxon.map.gz - | head -n 6


    7115    k:Bacteria,p:Firmicutes,c:Bacilli,o:Lactobacillales,f:Lactobacillaceae,g:Lactobacillus  3,63,186,874,2386,7115
    21349   k:Bacteria,p:Firmicutes,c:Bacilli,o:Lactobacillales,f:Lactobacillaceae,g:Lactobacillus,s:Lactobacillus acetotolerans    3,63,186,874,2386,7115,21349
    21350   k:Bacteria,p:Firmicutes,c:Bacilli,o:Lactobacillales,f:Lactobacillaceae,g:Lactobacillus,s:Lactobacillus acidophilus      3,63,186,874,2386,7115,21350
    21351   k:Bacteria,p:Firmicutes,c:Bacilli,o:Lactobacillales,f:Lactobacillaceae,g:Lactobacillus,s:Lactobacillus amylolyticus     3,63,186,874,2386,7115,21351
    21352   k:Bacteria,p:Firmicutes,c:Bacilli,o:Lactobacillales,f:Lactobacillaceae,g:Lactobacillus,s:Lactobacillus amylophilus      3,63,186,874,2386,7115,21352
    21353   k:Bacteria,p:Firmicutes,c:Bacilli,o:Lactobacillales,f:Lactobacillaceae,g:Lactobacillus,s:Lactobacillus amylovorus       3,63,186,874,2386,7115,21353


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-08-10 11:56 AM
