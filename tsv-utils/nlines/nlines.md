# tsv-utils之计算文件的行数-tsv-utils nlines

### 一、tsv-utils nlines介绍

**功能描述：**

`tsv-utils nlines`计算文件的行数，可添加输出结果的注释信息。

**命令行接口：**

    $ tsv-utils nlines
    
    Usage: tsv-utils nlines [options] <text>
    Options:
      -a  STR print auxiliary information. ie: sample_id;
      -i      flag to ignore lines start with '#';

**可选参数：**   

    -a  字符串    添加注释标签;
    -i           忽略以'#'开头的行;

### 二、使用场景实例及其用法

**示例演示：**

**示例文件：** `kofams.txt`

    $ cat kofams.txt | head -n 6


    #seqid  ko      threshold       score   evalue  domain_coverage query_coverage  definition      type
    Y1_g_00002      K03686  415.90  500.5   1.4e-150        0.50    0.98    molecular chaperone DnaJ
    Y1_g_00003      K04043  830.13  895.1   7.1e-270        0.79    0.99    molecular chaperone DnaK
    Y1_g_00004      K03687  30.90   186.6   1.1e-55 0.43    0.92    molecular chaperone GrpE
    Y1_g_00005      K03705  67.20   310.9   2.3e-93 0.79    0.98    heat-inducible transcriptional repressor
    Y1_g_00006      K02495  263.57  311.1   2.2e-93 0.71    0.97    oxygen-independent coproporphyrinogen III oxidase [EC:1.3.98.3]


**运行命令:** 

**参数使用1：** 设置参数`-a`，添加注释信息, 设置参数`-i`，忽略以'#'开头的行。

    $ tsv-utils  nlines  -i  -a "Y1"  kofams.txt


    Y1      1413


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 8/30/2020 7:11:08 PM
