# atlas-utils之获取双端序列的barcode序列：barcode

### 一、atlas-utils barcode介绍

**功能描述：**

`atlas-utils barcode` 从双端序列中获取barcode序列, 可以用来检查序列中存在哪些barcode序列,检查数据拆分的情况。

**命令行接口：**

    $ atlas-utils barcode
    
    Usage: atlas-utils barcode <1.fq> <2.fq>


### 二、使用场景实例及其用法


**使用场景经典案例：**

检查数据拆分率低，或者检查barcode是否有使用错了。

**示例演示：**

**示例文件：** `A-1_1.fastq`，`A-1_2.fastq`

    $ cat A-1_1.fastq | head -n 6


    $ cat barcode/example/A-1_1.fastq | head -n 6
    @HISEQ:483:HLJ2LBCXY:1:1101:7924:2136 1:N:0:CACCGG
    CCTATGGGACGCAGCAGTGGGGAATATTGGACAATGGGCGCAAGCCTGATCCAGCCATGCCGCGTGAGTGATGAAGGCCCTAGGGTTGTAAAGCCCTTTCGGCGGGGAAGATAATGACGGTACCCGCAGAAGAAGCCCCGGCTAACTTCGTGCCAGCAGCCGCGGTAATACGAAGGGGGCTAGCGTTGCTCGGAATTACTGGGCGTAAAGCGCACGTAGGCGGCTTTCTAAGTCGGGGGTGAA
    +
    HH1CHHHHDFHDHDH?C<DEG/CEHHIHEHCHECFHICHHHHHDHIICHHIEHCHCEGHHIICH?EEHFHHHIECEE?HE?1GHHHHDHHHHHFFGHHHCHHHII?H?HHEHCHF1CGHC0DEHEHHD<<FEHHHIGHIC??HHCGHHHHIHH@FFEEHIHDHHCHHIHIHE@GH-G??EDEGEHIHIICHHC?EHH-6@8-B-=C,5@@FHHHHHHHCEHH#####################
    @HISEQ:483:HLJ2LBCXY:1:1101:16730:2160 1:N:0:CACCGG
    CCTACGGGAGGCACCAGCAAGGAATTTTCCGCAATGGGCGAAAGCCTGACGGAGCAACGCCGCGTGGGGGATGAAGGCCTTCGGGTTGTAAACCCCTTTTGCGAGGGAAGAAGATCTGACGGTACCTCGCGAATAAGCCACGGCTAACTACGTGCCAGCAGCCGCGGTAATACGTAGGTGGCAAGCGTTGTCCGGATTTACTGGGCGTAAAGCGCGCGCAGGCGGACTGGTAAGTCTGGGGCG


    $ cat A-1_2.fastq | head -n 6


    @HISEQ:483:HLJ2LBCXY:1:1101:7924:2136 2:N:0:CACCGG
    GGACTACTTGGGTATCTAATCCTGTTTGCTCCCCACGCTTTCGCACCTCAGCGTCAGTACCGGGCCAGTGAGCCGCCTTCGCCACTGGTGTTCTTGCGAATATCTACGAGTTTCACCTCTACACTCGCAGTTCCACTCACCTCTCCCGGACTCGAGCTCTCCAGTATCGAAGGCAGTTCTGGAGTTAAGCTCCAGGAGTTCACCCCCGACTTAGAAAGCCGCCTACGTGCGCTTTACGCCCAGGC
    +
    HG1EG1F?CGEHGHCHH@GC1<@GEHE?GHHHIHHCHHHHEHE=EFHIHIGEDEC@GHHFH=HD?CCG1D1C?EDCCHCG10C00DGH@CCGHHIGD/C/CECHHEHIIGHECEHHHHHIIGHGFH@HIHEEHCGEHFHFDGHHIHEH,CCHHECHHHIHIGFABGC@EHICHHHFHHEHH?AG.AFBCHCAHHIHH-8B@C-.8>=>+6CEC@G@@EHHHCDH=CHE@@D+5@EEF--7CEG##
    @HISEQ:483:HLJ2LBCXY:1:1101:16730:2160 2:N:0:CACCGG
    GGACTACACGGGTATCTAATCCGGTTTGCTCCCCACGCTTTCGCGCCTCAGCGTCAGGTTGCCCCCAGAGAGTCGCTTTCGCCACTGGTGTTCCTCCCGATATCTACGCATTCCACCACTACACCGGGAATTCCACTCTCCTCTGAGCCCCTCAAGACCGGCAGTATCCGGGGACCGCTCACAGTTGAGCCGTGAGATTTCACCCCAGACTTACCAGCCCGCCTGCGCGCGCTTTACGCCCAGTA


**运行命令：**

获取`A-1`双端序列的`barcode`序列, 默认8个碱基;


    $ atlas-utils barcode -l 8 A-1_1.fastq A-1_2.fastq | head


    HISEQ:483:HLJ2LBCXY:1:1101:7924:2136    CCTATGGG        GGACTACT
    HISEQ:483:HLJ2LBCXY:1:1101:16730:2160   CCTACGGG        GGACTACA
    HISEQ:483:HLJ2LBCXY:1:1101:19412:2440   CCTATGGG        GGACTACT
    HISEQ:483:HLJ2LBCXY:1:1101:10790:2619   CCTACGGG        GGACTACT
    HISEQ:483:HLJ2LBCXY:1:1101:10004:2933   CCTATGGG        GGACTACA
    HISEQ:483:HLJ2LBCXY:1:1101:16103:2752   CCTATGGG        GGACTACG
    HISEQ:483:HLJ2LBCXY:1:1101:17844:2827   CCTATGGG        GGTCTACA
    HISEQ:483:HLJ2LBCXY:1:1101:5069:3192    CCTATGGG        GGACTACT
    HISEQ:483:HLJ2LBCXY:1:1101:11184:3127   CCTATGGG        GGACTACT
    HISEQ:483:HLJ2LBCXY:1:1101:11518:3202   CCTATGGG        GGACTACT


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-9 11:56 AM