# atlas-utils之生成 krona 兼容的文件格式：krona


### 一、atlas-utils krona介绍

**功能描述：**

`atlas-utils krona` 给定 `(Z)OTU`  表以及样本标识符，生成 `Krona` 兼容的文件格式。

**命令行接口：**

    $ atlas-utils krona
    
    Usage: atlas-utils krona <otutab:annotated> <sample>

### 二、使用场景实例及其用法


**示例演示：**

文件：`zotu_table_freqs_ann.txt`

    $ cat zotu_table_freqs_ann.txt | head


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2     taxonomy
    ZOTU_1  0       0       0.004627        0.01551 0.09528 0.1079  d:Bacteria,p:"Proteobacteria",c:Epsilonproteobacteria,o:Campylobacterales,f:Campylobacteraceae,g:Arcobacter
    ZOTU_2  0.008106        0.01835 0.06743 0.08831 0.002709        0.002064        d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Oceanospirillales,f:Halomonadaceae,g:Halomonas
    ZOTU_3  0       0       0.008615        0.00887 0.05814 0.06045 d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhodospirillales,f:Acetobacteraceae,g:Roseomonas
    ZOTU_4  0       0       0.005265        0.002789        0.06512 0.06497 d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_5  0       0       5.318e-05       0.0004463       0.06335 0.0641  d:Bacteria,p:"Bacteroidetes"
    ZOTU_6  3.635e-05       8.211e-05       0.0004786       0.0008926       0.06017 0.05797 d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhizobiales,f:Rhizobiaceae
    ZOTU_7  0       0       0.003882        0.002287        0.05439 0.05633 d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_8  0       0       0.07195 0.06867 0.0001042       2.991e-05       d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Alteromonadales,f:Alteromonadaceae,g:Alishewanella
    ZOTU_9  0       0       0.06233 0.05701 5.209e-05       5.983e-05       d:Bacteria,p:"Bacteroidetes",c:Flavobacteriia,o:"Flavobacteriales",f:Flavobacteriaceae,g:Flavobacterium

**运行命令：**

给定**(Z)OTU** 表以及样本标识符，生成 `Krona` 兼容的文件格式。

    $ atlas-utils krona zotu_table_freqs_ann.txt A-1 | head


    0.001309        d:Bacteria      p: Proteobacteria       c:Deltaproteobacteria   o:Myxococcales  f:Labilitrichaceae      g:Labilithrix
    0.00370755      d:Bacteria      p: Proteobacteria       c:Alphaproteobacteria   o:Rhizobiales   f:Rhizobiaceae  Rhizobiaceae_unclassified
    0.002036        d:Bacteria      p: Actinobacteria       c:Actinobacteria        o:Actinomycetales       f:Promicromonosporaceae g:Promicromonospora
    0.011996        d:Bacteria      p: Actinobacteria       c:Actinobacteria        o:Actinomycetales       f:Streptosporangiaceae
    0.0147543       d:Bacteria      p: Proteobacteria       c:Alphaproteobacteria   o:Rhizobiales   f:Bradyrhizobiaceae     Bradyrhizobiaceae_unclassified
    3.635e-05       d:Bacteria      p: Actinobacteria       c:Actinobacteria        o:Actinomycetales       f:Demequinaceae
    0.001272        d:Bacteria      p: Proteobacteria       c:Gammaproteobacteria   o:Xanthomonadales       f:Sinobacteraceae       Sinobacteraceae_unclassified
    0.0004362       d:Bacteria      p: Bacteroidetes        c:Sphingobacteriia      o: Sphingobacteriales   f:Chitinophagaceae      g:Chitinophaga  s:Chitinophaga_taiwanensis
    0.0249409       d:Bacteria      p: Bacteroidetes        c:Sphingobacteriia      o: Sphingobacteriales   f:Chitinophagaceae      g:Arachidicoccus        s:Arachidicoccus_rhizosphaerae
    0.003199        d:Bacteria      p: Actinobacteria       c:Actinobacteria        o:Actinomycetales       f:Mycobacteriaceae      g:Mycobacterium s:Mycobacterium_phlei


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

