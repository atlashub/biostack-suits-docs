# tsv-utils之注释文件关联和描述: links

### 一、tsv-utils links介绍

**功能描述：**

`tsv-utils links`  在 `associate `的基础上添加了对新的 `value` 的文字描述。

**命令行接口：**

    $ tsv-utils links
    
    Usage: tsv-utils links <feature-map> <links> <links-definition>



### 二、使用场景实例及其用法

**示例演示**

**示例文件：** 

`KEGG` 功能能注释，`ko`等级关联至更高级别，比如`Module`

**示例文件：** `ko.txt, ko-module.txt`


    $ cat  ko.txt  | head -n6


    #seqid  ko
    TRINITY_g100334_i1_1    K00370
    TRINITY_g100485_i1_1    K00260
    TRINITY_g101100_i1_1    K00262
    TRINITY_g101136_i1_1    K01455
    TRINITY_g102554_i1_1    K00370


    $ cat ko-pathway.txt | head -n6


    K00001  map00010
    K00002  map00010
    K00016  map00010
    K00114  map00010
    K00121  map00010
    K00128  map00010


    $ cat pathway-definition.txt  | head -n6


    map00010        Glycolysis / Gluconeogenesis
    map00020        Citrate cycle (TCA cycle)
    map00030        Pentose phosphate pathway
    map00040        Pentose and glucuronate interconversions
    map00051        Fructose and mannose metabolism
    map00052        Galactose metabolism


**运行命令:**


    $ tsv-utils  links  ko.txt   ko-pathway.txt  pathway-definition.txt | head -n 6


    TRINITY_g100334_i1_1    map00910        Nitrogen metabolism
    TRINITY_g100334_i1_1    map01100        Metabolic pathways
    TRINITY_g100334_i1_1    map01120        Microbial metabolism in diverse environments
    TRINITY_g100334_i1_1    map02020        Two-component system
    TRINITY_g100485_i1_1    map00220        Arginine biosynthesis
    TRINITY_g100485_i1_1    map00250        Alanine, aspartate and glutamate metabolism


`注意事项:` 文件顺序, 第一个输入文件为转录本的, `Transcript -> KO`注释文件, 第二个为KEGG的提升分类(`pathway`)映射表(`ko -> pathway`),第一列为需要关联的主键, 第三个文件为提升等级(`pathway`)的注释信息.



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 7:03:58 PM