# atlas-utils之使用SINTAX/RDP结果注释(Z)OTU表：annotation

### 一、atlas-utils annotation介绍

**功能描述：**

`atlas-utils annotation` 使用SINTAX/RDP结果注释`(Z)OTU`表。

**命令行接口：**

    $ atlas-utils annotation
    
    Usage: atlas-utils annotation <annotation> <otutab>


### 二、使用场景实例及其用法

**使用场景经典案例：**

1. 扩增子数据分析, 对 `ZOTU` 进行注释;

**示例演示：**

文件：`classify.txt`，`zotu_table.txt`


    $ cat classify.txt | head -n 5


    ZOTU_19 d:Bacteria(1.0000),p:"Bacteroidetes"(1.0000),c:Sphingobacteriia(1.0000),o:"Sphingobacteriales"(1.0000),f:Chitinophagaceae(1.0000),g:Parafilimonas(0.9400),s:Parafilimonas_terrae(0.8836)      +       d:Bacteria,p:"Bacteroidetes",c:Sphingobacteriia,o:"Sphingobacteriales",f:Chitinophagaceae,g:Parafilimonas,s:Parafilimonas_terrae
    ZOTU_5  d:Bacteria(1.0000),p:"Bacteroidetes"(1.0000),c:"Bacteroidia"(0.7800),o:"Bacteroidales"(0.6084),f:Prolixibacteraceae(0.3650),g:Mariniphaga(0.0621),s:Mariniphaga_anaerophila(0.0105)   +       d:Bacteria,p:"Bacteroidetes"
    ZOTU_9  d:Bacteria(1.0000),p:"Bacteroidetes"(1.0000),c:Flavobacteriia(1.0000),o:"Flavobacteriales"(1.0000),f:Flavobacteriaceae(1.0000),g:Flavobacterium(1.0000)       +       d:Bacteria,p:"Bacteroidetes",c:Flavobacteriia,o:"Flavobacteriales",f:Flavobacteriaceae,g:Flavobacterium
    ZOTU_12 d:Bacteria(1.0000),p:"Bacteroidetes"(1.0000),c:"Bacteroidia"(1.0000),o:"Bacteroidales"(1.0000),f:"Porphyromonadaceae"(1.0000),g:Petrimonas(1.0000),s:Petrimonas_sulfuriphila(1.0000)  +       d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae",g:Petrimonas,s:Petrimonas_sulfuriphila
    ZOTU_7  d:Bacteria(1.0000),p:"Bacteroidetes"(1.0000),c:"Bacteroidia"(1.0000),o:"Bacteroidales"(1.0000),f:"Porphyromonadaceae"(1.0000),g:Macellibacteroides(0.5700),s:Macellibacteroides_fermentans(0.3249)    +       d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"

    $ cat zotu_table.txt | head


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2
    ZOTU_1  0       0       87      278     1829    3608
    ZOTU_2  223     447     1268    1583    52      69
    ZOTU_3  0       0       162     159     1116    2021
    ZOTU_4  0       0       99      50      1250    2172
    ZOTU_5  0       0       1       8       1216    2143
    ZOTU_6  1       2       9       16      1155    1938
    ZOTU_7  0       0       73      41      1044    1883
    ZOTU_8  0       0       1353    1231    2       1
    ZOTU_9  0       0       1172    1022    1       2


**运行命令：**

使用对应的物种注释注释对应OTU表。


    $ cut -f1,4 classify.txt | atlas-utils annotation  - zotu_table.txt | head


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


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-9 11:56 AM

