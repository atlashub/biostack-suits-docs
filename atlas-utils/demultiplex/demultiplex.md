# atlas-utils之使用双端**barcode**拆分数据：demultiplex

### 一、atlas-utils demultiplex介绍

**功能描述：**

`atlas-utils demultiplex` 使用双端**barcode**拆分数据，之支持精确匹配模式。

**命令行接口：**

    $ atlas-utils demultiplex
    
    Usage: atlas-utils demultiplex [options]
    Options:
      -1 STR  forward reads file;
      -2 STR  reverse reads file;
      -b STR  barcode mapping file;
      -d STR  output filename directory;
      -l INT  minimum barcode length, default: 5;
      -h      display usage;
    
    Example:
    atlas-utils  demutiplex  -b barcodes.txt -1 I365.R1.fastq.gz  -2  I365.R2.fastq.gz -l 5  -d  I365


**可选参数：**

      -1 字符串  正向序列文件;
      -2 字符串  反向序列文件;
      -b 字符串  barcode 映射文件;
      -d 字符串  输出文件夹名称;
      -l 字符串  最小barcode长度，默认为5;
      -h        显示用法; 

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：**`barcodes.txt`

    $ cat  barcodes.txt


    D001    TACCGGAA        GCCCTGTA
    D002    CTGCTACA        TAAATGCG

**运行命令：**

    $ cd example
    $ ls
    
    A1.1.fastq.gz  A1.2.fastq.gz  barcodes.txt   
    
    $ atlas-utils  demultiplex -b barcodes.txt -1  A1.1.fastq.gz -2  A1.2.fastq.gz -l 5 -d A1
    $ tree -L 2


        .
    ├── A1
    │   ├── D001_1.fastq
    │   ├── D001_2.fastq
    │   ├── D002_1.fastq
    │   └── D002_2.fastq
    ├── A1.1.fastq.gz
    ├── A1.2.fastq.gz
    └── barcodes.txt



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-09 11:56 AM

