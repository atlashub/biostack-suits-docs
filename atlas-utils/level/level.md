# atlas-utils之计算指定分类学等级的丰度：level

### 一、atlas-utils level介绍

**功能描述：**

`atlas-utils level` 计算给定**(Z)OTU**表统计指定分类学等级的丰度。

**命令行接口：**

    $ atlas-utils level
    
    Usage: atlas-utils level [options] <otutab:annotated>

    Options:
      -l  taxonomy level in [dpcofgs] Default:['g']

**可选参数：**

      -l   指定分类学等级，默认为'g'；

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**`zotu_table_freqs_ann.txt`

    $ cat zotu_table_freqs_ann.txt | head -n 5


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2     taxonomy
    ZOTU_1  0       0       0.004627        0.01551 0.09528 0.1079  d:Bacteria,p:"Proteobacteria",c:Epsilonproteobacteria,o:Campylobacterales,f:Campylobacteraceae,g:Arcobacter
    ZOTU_2  0.008106        0.01835 0.06743 0.08831 0.002709        0.002064        d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Oceanospirillales,f:Halomonadaceae,g:Halomonas
    ZOTU_3  0       0       0.008615        0.00887 0.05814 0.06045 d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhodospirillales,f:Acetobacteraceae,g:Roseomonas
    ZOTU_4  0       0       0.005265        0.002789        0.06512 0.06497 d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"


**运行命令：**

计算给定**(Z)OTU**表统计属水平的丰度。

    $ atlas-utils level zotu_table_freqs_ann.txt | head


    #level  A-1     A-2     B-1     B-2     C-1     C-2
    Parvibaculum    0.0003635       0.0002874       5.318e-05       0       0.004845        0.004367
    Agromyces       0       0       0       0       0.009585        0.0114
    Pigmentiphaga   0.0001091       0.0001642       0.002765        0.001841        5.209e-05       0
    Mangrovibacterium       0       0       0.002499        0.001785        0       0
    Pseudonocardia  0.001891        0.001683        0       0       0       0
    Lactococcus     0.003272        0.004475        0       0       0       0
    Chelativorans   0.002945        0.003079        0       0       0       0
    Olivibacter     0.001818        0.001684        0       0       0       0
    Brevundimonas   0.0001818       4.105e-05       0.00335 0.007978        0.002761        0.00353

**参数选项1：** 设置 `-l` 参数，改为计算科水平的丰度。


    $ atlas-utils level -l f zotu_table_freqs_ann.txt | head


    #level  A-1     A-2     B-1     B-2     C-1     C-2
    Streptococcaceae        0.003563        0.004803        0       0       0       0
    Spirochaetaceae 0       0       0.0005318       0.0004463       0.0087  0.007628
    Moraxellaceae   0       0       0.006116        0.04151 0.00224 0.002124
    Acetobacteraceae        0.0012  0.001478        0.008615        0.008926        0.06111 0.06365
    Pseudonocardiaceae      0.007744        0.00899 0       0       0       0
    Cellulomonadaceae       0       0       0.001755        0.007642        0.002396        0.002482
    Campylobacteraceae      0       0       0.02765 0.03721 0.09533 0.1081
    Alteromonadaceae        0       0       0.1083  0.1044  0.0001042       2.991e-05
    Clostridiaceae_1        0       0       0.01888 0.01975 0.002292        0.002602


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

