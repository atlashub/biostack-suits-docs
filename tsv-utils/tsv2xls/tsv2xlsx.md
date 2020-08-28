# tsv-utils之使用libxlsxwriter组合多个制表符文件：tsv2xlsx

标签： tsv-utils

---

###一、tsv-utils tsv2xlsx介绍

**功能描述：**

`tsv-utils  tsv2xlsx`  **转换多个文件到** `EXCE` 文件的不同 `sheet`

tsv2xlsx 目的是将一堆制表符分隔的文本文件转换成Excel文件（xlsx格式，不是xls），转换成 xlsx 后体积会变小不少。

### ` libxlsxwriter 介绍`

`libxlsxwriter` 提供了很简洁的创建Excel文件的函数接口，100% 兼容xlsx，  [官方文档][2] 介绍的很详细，有很多实例， 接口都很简单，可以创建各种图形，是自动化生成Excel文档的不二选择。

下面是 `libxlsxwriter` 的其它语言接口：

 - Python [XlsxWriter][4] 
 - D [xlsxwriter][5] 
 - R [writexl][6] 
 - Perl [excel-writer-xlsx][7] 

 **命令行接口**


    $ tabtk_xlsx
    Usage: tabtk_xlsx  <xlsx> <sheet:file_path> [<sheet:file_path>]
    version: 0.0.1

接口很简单，变量第一个位置为输入xlsx文件名称， 后面为需要转换的文件列表，格式为 sheet名称：文件路径名称

###二、使用场景实例及其用法



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有.


Last Upate: 2017-10-12 2:52 PM

[1]: https://github.com/jmcnamara/libxlsxwriter
[2]: https://libxlsxwriter.github.io/
[3]: https://libxlsxwriter.github.io/demo.png
[4]: https://github.com/jmcnamara/XlsxWriter
[5]: https://github.com/economicmodeling/xlsxwriter
[6]: https://github.com/renkun-ken/writexl
[7]: https://github.com/jmcnamara/excel-writer-xlsx