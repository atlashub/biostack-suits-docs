# atlas-utils之计算对应样本的丰度：abundance

### 一、atlas-utils abundance介绍

**功能描述：**

`atlas-utils abundance` 给定 **(Z)OTU** 表以及样本标识符，计算对应样本的丰度。

**命令行接口：**

    $ atlas-utils abundance
    
    Usage: atlas-utils abundance [options] <otutab:annotated> <sample>
    
    Options:
      -l  taxonomy level in [dkcofgs] Default:['g']

**可选参数：**

      -l   指定分类学等级，默认为'g'；

### 二、使用场景实例及其用法

**使用场景经典案例：**

1. 扩增子数据分析, 计算样本的在不同分类水平的相对丰度;

**示例演示：**

**示例文件：** `zotu_table_freqs_ann.txt`

    $ cat zotu_table_freqs_ann.txt | head -n 10


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2     taxonomy
    ZOTU_1  0       0       87      278     1829    3608    d:Bacteria,p:"Proteobacteria",c:Epsilonproteobacteria,o:Campylobacterales,f:Campylobacteraceae,g:Arcobacter
    ZOTU_2  223     447     1268    1583    52      69      d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Oceanospirillales,f:Halomonadaceae,g:Halomonas
    ZOTU_3  0       0       162     159     1116    2021    d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhodospirillales,f:Acetobacteraceae,g:Roseomonas
    ZOTU_4  0       0       99      50      1250    2172    d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_5  0       0       1       8       1216    2143    d:Bacteria,p:"Bacteroidetes"
    ZOTU_6  1       2       9       16      1155    1938    d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhizobiales,f:Rhizobiaceae
    ZOTU_7  0       0       73      41      1044    1883    d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_8  0       0       1353    1231    2       1       d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Alteromonadales,f:Alteromonadaceae,g:Alishewanella
    ZOTU_9  0       0       1172    1022    1       2       d:Bacteria,p:"Bacteroidetes",c:Flavobacteriia,o:"Flavobacteriales",f:Flavobacteriaceae,g:Flavobacterium


`注意事项:` 文件格式使用 `d:Bacteria`.

**运行命令：**

计`A-1`的丰度，默认为属水平。


    $ atlas-utils abundance ./zotu_table_freqs_ann.txt  A-1 | head -n 10


    #taxonomy       abundance
    Parvibaculum    10
    Pigmentiphaga   3
    Pseudonocardia  52
    Lactococcus     90
    Chelativorans   81
    Olivibacter     50
    Brevundimonas   5
    Pseudomonas     84
    Sphingopyxis    303


**参数选项1：** 设置 ` -l` 参数，该为计算科水平丰度。


    $ atlas-utils abundance -l f ./zotu_table_freqs_ann.txt  A-1 | head -n 10


    #taxonomy       abundance
    Streptococcaceae        98
    Acetobacteraceae        33
    Pseudonocardiaceae      213
    Microbacteriaceae       265
    Sneathiellaceae 14
    Thermomonosporaceae     246
    Caulobacteraceae        32
    Mycobacteriaceae        422
    Rhizobiaceae    159


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-9 11:56 AM