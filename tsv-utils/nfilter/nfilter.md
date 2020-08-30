# tsv-utils之数值型制表符文件标准化：nfilter

### 一、tsv-utils nfilter 介绍

**功能描述：**

`tsv-utils nfilter` 对数值表进行过滤行操作，通过指定某一列，将该列大于或者小于设定阈值的行过滤掉；

**命令行接口：**

    $ tsv-utils nfilter
    
    Usage: tsv-utils nfilter <tsv> <value>
    
        Options:
        -f  INT    fileld for compare. default: [2].
        -l  FLAG   print line if: value larger than specified fields.


**可选参数**


        -f 指定   指定某一列用来与阈值进行比较，默认指定为第二列
        -l 标识符 如果添加该参数则将过滤掉小于阈值的行，不添加则过滤掉大于阈值的行


### 二、使用场景实例及其用法


**示例演示**

**示例文件：** `zotu_table_ann.txt`


    $ cat zotu_table_ann.txt  |head -n 6


    #OTU ID A-1     A-2     B-1     B-2     C-1     C-2     taxonomy
    ZOTU_1  0       0       87      278     1829    3608    d:Bacteria,p:"Proteobacteria",c:Epsilonproteobacteria,o:Campylobacterales,f:Campylobacteraceae,g:Arcobacter
    ZOTU_2  223     447     1268    1583    52      69      d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Oceanospirillales,f:Halomonadaceae,g:Halomonas
    ZOTU_3  0       0       162     159     1116    2021    d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhodospirillales,f:Acetobacteraceae,g:Roseomonas
    ZOTU_4  0       0       99      50      1250    2172    d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_5  0       0       1       8       1216    2143    d:Bacteria,p:"Bacteroidetes"


**运行命令：**

打印出 `zotu_table_ann.txt` 中`A-1` 样本 ZOTU reads数少于`1000` 的行。

    $ cut -f1,2,8 zotu_table_ann.txt  | tsv-utils  nfilter -f2  -  500  | head -n 10


    #OTU ID A-1     taxonomy
    ZOTU_1  0       d:Bacteria,p:"Proteobacteria",c:Epsilonproteobacteria,o:Campylobacterales,f:Campylobacteraceae,g:Arcobacter
    ZOTU_2  223     d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Oceanospirillales,f:Halomonadaceae,g:Halomonas
    ZOTU_3  0       d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhodospirillales,f:Acetobacteraceae,g:Roseomonas
    ZOTU_4  0       d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_5  0       d:Bacteria,p:"Bacteroidetes"
    ZOTU_6  1       d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhizobiales,f:Rhizobiaceae
    ZOTU_7  0       d:Bacteria,p:"Bacteroidetes",c:"Bacteroidia",o:"Bacteroidales",f:"Porphyromonadaceae"
    ZOTU_8  0       d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Alteromonadales,f:Alteromonadaceae,g:Alishewanella
    ZOTU_9  0       d:Bacteria,p:"Bacteroidetes",c:Flavobacteriia,o:"Flavobacteriales",f:Flavobacteriaceae,g:Flavobacterium


打印出 `zotu_table_ann.txt` 中`A-1` 样本 ZOTU reads数少于`10000` 的行, 使用参数 `-l`;

    $ cut -f1,2,8 zotu_table_ann.txt  | tsv-utils  nfilter  -l -f2  -  500  | head -n 10


    #OTU ID A-1     taxonomy
    ZOTU_16 860     d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhodospirillales
    ZOTU_17 829     d:Bacteria,p:"Bacteroidetes",c:Sphingobacteriia,o:"Sphingobacteriales",f:Chitinophagaceae
    ZOTU_19 779     d:Bacteria,p:"Bacteroidetes",c:Sphingobacteriia,o:"Sphingobacteriales",f:Chitinophagaceae,g:Parafilimonas,s:Parafilimonas_terrae
    ZOTU_20 694     d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhizobiales
    ZOTU_21 724     d:Bacteria,p:"Proteobacteria",c:Gammaproteobacteria,o:Xanthomonadales,f:Xanthomonadaceae
    ZOTU_23 603     d:Bacteria,p:"Acidobacteria",c:Acidobacteria_Gp3,g:Gp3
    ZOTU_24 550     d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Rhizobiales,f:Phyllobacteriaceae
    ZOTU_26 607     d:Bacteria,p:"Proteobacteria",c:Alphaproteobacteria,o:Sphingomonadales,f:Erythrobacteraceae
    ZOTU_28 550     d:Bacteria,p:"Actinobacteria",c:Actinobacteria,o:Actinomycetales,f:Nocardioidaceae,g:Aeromicrobium


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 8:15:15 PM