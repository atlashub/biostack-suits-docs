# tsv-utils之使用libxlsxwriter组合多个制表符文件：tsv2xlsx



### 一、tsv-utils tsv2xlsx介绍

**功能描述：**

`tsv-utils  tsv2xlsx`  **转换多个文件到** `EXCE` 文件的不同 `sheet`

`tsv2xlsx` 目的是将一堆制表符分隔的文本文件转换成 `Excel` 文件（xlsx格式，不是xls），转换成 `xlsx` 后体积会变小不少，`tsv2xlsx`  通过 `libxlsxwrite` 库文件实现。

![](https://libxlsxwriter.github.io/demo.png)

### `libxlsxwriter 介绍`

`libxlsxwriter` 提供了很简洁的创建Excel文件的函数接口，100% 兼容xlsx，  [官方文档][1] 介绍的很详细，有很多实例， 接口都很简单，可以创建各种图形，是自动化生成Excel文档的不二选择。

下面是 `libxlsxwriter` 的其它语言接口：

 - Python [XlsxWriter][4] 
 - D [xlsxwriter][5] 
 - R [writexl][6] 
 - Perl [excel-writer-xlsx][7] 

 **命令行接口**


    $ tsv-utils tsv2xlsx
    
    Usage: tsv-utils tsv2xlsx  <xlsx> [sheet-name:file_path ...]


接口很简单，变量第一个位置为输入xlsx文件名称， 后面为需要转换的文件列表，格式为 `sheet名称`：`文件路径名称`


### 二、使用场景实例及其用法

**使用场景经典案例：**

 许多文件需要需要整合到Excel进行整体交付，比如: 16S 扩增子数据分析，可以将`class  family  genus  order  phylum` 的分类信息整合到一个Excel 文档。

**示例演示：**

文件列表：`class.freqs.txt  family.freqs.txt  genus.freqs.txt  order.freqs.txt  phylum.freqs.txt`

    cat  phylum.freqs.txt | head -n 6
    
    #level  A-1     A-2     B-1     B-2     C-1     C-2
    "Chrysiogenetes"        0       0       0.007925        0.005522        5.211e-05       0
    "Fusobacteria"  0       0       0.002287        0.00145 0       0
    Above_phylum    0.02955 0.02763 0.001702        0.0006135       0.006513        0.007059
    Firmicutes      0.009595        0.01371 0.05734 0.05388 0.01891 0.01825
    "Gemmatimonadetes"      0.003235        0.002874        0       0       0       0

**运行命令：**

    tsv-utils   tsv2xlsx  taxonomy.xlsx   phylum:phylum.freqs.txt  class:class.freqs.txt  family:family.freqs.txt  order:order.freqs.txt  genus:genus.freqs.txt



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有.


Last Upate: Friday, August 28, 2020

[1]: https://github.com/jmcnamara/libxlsxwriter
[2]: https://libxlsxwriter.github.io/
[3]: https://libxlsxwriter.github.io/demo.png
[4]: https://github.com/jmcnamara/XlsxWriter
[5]: https://github.com/economicmodeling/xlsxwriter
[6]: https://github.com/renkun-ken/writexl
[7]: https://github.com/jmcnamara/excel-writer-xlsx