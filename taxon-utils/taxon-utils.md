
# taxon-utils: taxon 数据操作工具

### 一、程序介绍

`taxon-utils` 为一组处理`taxon`信息的程序集合，主要使用`klib` 进行开发，包括`khash, kvect, kstring`等。

### 二、主程序接口

当前释放版本： `version：0.0.1-r1`

    $ taxon-utils

    Usage:   taxon-utils <command> <arguments>
    Version: 0.0.1-r1

    Command:
          translate   translate the taxon_id map to lineage.
          lineage     translate the taxon_id map to full lineage.
          name        translate the taxon_id map to name.
          lca         perform lca for given taxon match per query.
          bin         bin reads for specify level. default: [species] .
          clade       get clade taxon id from NCBI taxonomy tree.
          filter      filter the entries with specified taxonIds.

    Licenced:
    (c) 2018-2020 - LEI ZHANG
    Logic Informatics Co.,Ltd.
    zhanglei@logicinformatics.com


### 三、主要子命令功能介绍

主要子命令功能介绍：

1. [translate](translate/translate.md) ： 指定的特定节点或者节点列表，使用构建的节点树文件，回溯到根节点，输出中间节点的路径。
2. [lineage](lineage/lineage.md)  ： 指定的特定节点或者节点列表，使用构建的节点树文件，回溯到根节点，输出中间节点的路径。
3. [name](name/name.md)  ： 指定的特定节点或者节点列表，输出对应的科学命令。
4. [lca](lca/lca.md) ：对提供的多个节点，从物种树中寻找共同祖先，输出对应的共同祖先节点。
5. [bin](bin/bin.md) ：将所有分类都归并到指定的分类水平,比如门水平。
6. [clade](clade/clade.md) ：提供一个节点，返回该节点在树中的说有子节点。
7. [filter](filter/filter.md) ： 适配程序，过滤掉指定的节点（包含其所有子节点），使用场景：Kraken序列分类中去除特定分类的比对结果，比如病毒，或者真菌类。


本文材料为 BASE (Biostack Applied bioinformatic SEies ) 课程 Linux Command Line Tools for Life Scientists 材料， 版权归 上海逻捷信息科技有限公司 所有。

Last Update: 9/13/2020 8:14:45 PM