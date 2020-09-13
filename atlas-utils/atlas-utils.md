
# atlas-utils: 微生物组数据操作通用程序

### 一、程序介绍

    `atlas-utils` 为一组微生物组数据分析的工具包，主要使用`klib` 进行开发，包括`khash, kvect, kstring`等。

### 二、主程序接口

当前释放版本： `version：0.0.1-r2`

    $ atlas-utils
    
    Usage:   atlas-utils <command> <arguments>
    Version: 0.0.1 r2
    
    Command:
          -- Fastq manipulation.
             demultiplex       FASTAQ demultiplex with barcode sequence.
             split             FASTAQ demultiplex with barcode without
                               trimming barcode sequence.
             uniques           Find unique sequences and abundances.
             linkpairs         Link paired-reads with padding 'N'.
             fqchk             Fastq QC (base/quality summary).
             label             Add label to fasta headline.
             barcode           Get barcode seq from paired-reads.
             orient            Orient seq use strand +/- information.
             primer_strip      Retrive sequence region matches to primer pair.
                               support single end match.
    
          -- (Z)OTU manipulation.
             unique_table     Construct uniques table using exact match.
             annotation       Annotate OTU table using OTU assignment from Sintax/RDP.
             filter           1. Filter sequence from Mitochondria/Chloroplast, 2. optional filter
                              specifed taxon level .
             level            Abundance table for specify taxonomy level. ie. genus.
             abundance        Abundance table for specify taxonomy level and sample. ie. genus.
             summary          Calcuate OTU number/Tag number per sample.
             rowsum           Calcuate row sum.
             rank             Rank/merge for numeric table.
             krona            Convert annotated OTU table to krona text format.
             quantile         Calcuate  nth quantile sample size for otu_table normalization.
             mean_size        Calcuate 'Mean' sample size for otu_table normalization.
             min_size         Calcuate 'Min' sample size for otu_table normalization.
             max_size         Calcuate 'Max' sample size for otu_table normalization.
             counts2freqs     Convert counts table from counts to frequencies.
             trim             Delete low-abundance (Z)OTUs.
             binary           Convert (Z)OTUs table to presence/absence values.
             pairwise         Convert (Z)OTUs table to pairwise format for phylocom.
             rarity           rarity summary.
             rare             Rarefy OTU table to specified number of reads.
             group_by         group_by operation for OTU table, support average, sum.
    
          -- PICRUSt.
             normalization    Normalize OTU table with 16S copy Number, et..
             melt             Calculate feature abundance. ie. KEGG, COG, with Greengene 13.5.
             kann             Calculate feature abundance using feature maps, KO -> Module.
    
          -- auxiliary utils.
             view             View text file, ignor comments and blank lines.
             getline          Get target line with headline.
             subsamples       Get target columns with headline match.
             partition        Split OTU table into specify number file.

    Licenced:
    (c) 2019-2020 - LEI ZHANG
    Logic Informatics Co.,Ltd.
    zhanglei@logicinformatics.com


### 三、主要子命令功能介绍

主要子命令功能介绍：


1. [demultiplex](./demultiplex/demultiplex.md)       使用双端`barcode`拆分数据，支持精确匹配模式,去除`barcode`序列;
2. [split](./split/split.md)                   使用双端`barcode`拆分数据，支持精确匹配模式,不去除`barcode`序列;
3. [uniques](./uniques/uniques.md)             计算非冗余序列，兼容USEARCH的注释文件；
4. [linkpairs](./linkpairs/linkpairs.md)             链接PE双端序列，中间填充指定数量’N’；
5. [fqchk](./fqchk/fqchk.md)                 统计序列质量；
6. [label](./label/label.md)                  标注序列文件的注释信息；
7. [barcode](./barcode/barcode.md)            获取PE序列的 5‘->3’ 前指定数量碱基作为barcode，适用于检测序列未拆分信息；
8. [orient](./orient/orient.md)                调整序列的方向,根据数据库的 +/- 链特异性；
9. [primer_strip](./primer_strip/primer_strip.md)      切除引物序列;
10. [unique_table](./unique_table/unique_table.md)     使用USEATCH unique子命令构建Unique序列丰度表；
11. [annotation](./annotation/annotation.md)         使用SINTAX/RDP结果注释(Z)OTU表；
12. [filter](./filter/filter.md)                   过滤USEARCH SINTAX/NBC分类结果中线粒体和叶绿体来源的序列，可以指定匹配的分类学名称；
13. [level](./level/level.md)                  计算给定(Z)OTU表统计指定分类学等级的丰度；
14. [abundance](./abundance/abundance.md)        给定(Z)OTU表以及样本标识符，计算对应样本的丰度；
15. [summary](./summary/summary.md)           计算给定(Z)OTU表的(Z)OTU数目以及Tags数目；
16. [rowsum](./rowsum/rowsum.md)             计算ZOTU表中的每个(Z)OTU 的Tags数；
17. [rank](./rank/rank.md)                   对给定(Z)OTU表进行排序，并输出指定数据的 (Z)OTU 或者物种分类，其余可归并到Others分类；
18. [krona](./krona/krona.md)                 给定(Z)OTU 表以及样本标识符，生成Krona兼容的文件格式；
19. [quantile](./quantile/quantile.md)             计算样本Tags数指定百分比大小数值；
20. [mean_size](./mean_size/mean_size.md)        给定(Z)OTU表中所有样本的Tags总数的mean值；
21. [min_size](./min_size/min_size.md)           给定(Z)OTU表中所有样本的Tags总数的min值；
22. [max_size](./max_size/max_size.md)          给定(Z)OTU表中所有样本的Tags总数的max值；
23. [counts2freqs](./counts2freqs/counts2freqs.md)    将(Z)OTU表的counts 转换成相对丰度表；
24. [trim](./trim/trim.md)                   使用 (Z)OTU 相对丰度的和对(Z)OTU表进行过滤。
25. [binary](./binary/binary.md)               转换 (Z)OTU 表为presence/absence（0/1）模式；
26. [pairwise](./pairwise/pairwise.md)           转换(Z)OTU 表为三列 phylocom 格式；
27. [rarity](./rarity/rarity.md)                稀有度分析；
28. [rare](./rare/rare.md)                 (Z)OTU表抽平；
29. [group_by](./group_by/group_by.md)        根据分组信息汇总(Z)OTU表
30. [melt](./melt/melt.md)                根据Closed_OTU表预测功能多样性
31. [normalization](./normalization/normalization.md)  根据标记基因拷贝数对扩增子数据进行标准化；
32. [kann](./kann/kann.md)              用丰度表以及特征映射表，将数值表转换成更高级分类的数值表；比如KO表转换成Pathway表；
33. [view](./view/view.md)               简单处理表格行操作，比如添加注释符号（#），忽略注释符号以及空行；
34. [getline](./getline/getline.md)            根据指定的行标识符（与第一列的名称匹配），获取对应的行；
35. [subsamples](./subsamples/subsamples.md)    根据指定的列标识符（第一行中指定的名称），获取对应的列或者多列信息，强制包含第一列信息，比如从 (Z)OTU 表中抽取一部分样本的数值，形成新的 (Z)OTU 表；
36. [partition](./partition/partition.md)          根据指定样本数拆分(Z)OTU表;


本文材料为 BASE (Biostack Applied bioinformatic SEies ) 课程 Linux Command Line Tools for Life Scientists 材料， 版权归 上海逻捷信息科技有限公司 所有。

Last Update: 9/2/2020 12:19:31 AM