# tsv-utils 之制表符添加表头： add_headline

### 一、tsv-utils add_headline 介绍

**功能描述：**

`tsv-utils add_headline` 主要功能为对制表符文件添加表头；

**命令行接口：**

    $ tsv-utils add_headline
    
    Usage: tsv-utils add_headline <header: "string"> <text>


### 二、使用场景实例及其用法

**使用场景经典案例：**

1. BLAST 表格输出文件，添加制表符文件表头，让文档更易懂。

**示例演示：**

**示例文件：** `megablast.txt，SILVA_123_SSURef.txt` 

    $ cat  blastn.txt | head -n6


    ZOTU_1  JQ088343.1.1479 100.000 404     0       0       1       404     355     758     0.0     747
    ZOTU_2  JF138741.1.1356 100.000 429     0       0       1       429     323     751     0.0     793
    ZOTU_3  LN568336.1.1321 98.765  405     4       1       1       404     298     702     0.0     719
    ZOTU_4  FJ672447.1.1441 99.764  424     1       0       1       424     355     778     0.0     778
    ZOTU_5  EU542474.1.1489 100.000 424     0       0       1       424     353     776     0.0     784
    ZOTU_6  JQ072613.1.1343 100.000 404     0       0       1       404     270     673     0.0     747


**运行命令：**

    $ tsv-utils add_headline  "#qseqid\tsseqid\tpident\tlength\tmismatch\tgapopen\tqstart\tqend\tsstart\tsend\tevalue\tbitscore" megablast.txt  | head   -n6


    #qseqid sseqid  pident  length  mismatch        gapopen qstart  qend    sstart  send    evalue  bitscore
    ZOTU_1  JQ088343.1.1479 100.000 404     0       0       1       404     355     758     0.0     747
    ZOTU_2  JF138741.1.1356 100.000 429     0       0       1       429     323     751     0.0     793
    ZOTU_3  LN568336.1.1321 98.765  405     4       1       1       404     298     702     0.0     719
    ZOTU_4  FJ672447.1.1441 99.764  424     1       0       1       424     355     778     0.0     778
    ZOTU_5  EU542474.1.1489 100.000 424     0       0       1       424     353     776     0.0     784


本文材料为 BASE (Biostack Applied bioinformatic SEies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归上海逻捷信息科技有限公司所有。

Last Update: 8/30/2020 7:21:56 PM
