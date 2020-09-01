# fastx-utils之获得反向互补序列：revcomp

### 一、fastx-utils revcomp介绍

**功能描述：**

`fastx-utils revcomp`根据提供的序列进行反向互补。

**命令行接口：**

    $ fastx-utils revcomp
    
    Usage: fastx-utils revcomp <sequence>


### 二、使用场景实例及其用法

**示例演示：**

**运行命令：** 获得反向互补序列, 支持兼并碱基。


    $ fastx-utils revcomp CCTATGGGACGCAGCAGTGGGGAATATT
    
    AATATTCCCCACTGCTGCGTCCCATAGG


    $ fastx-utils revcomp  CCTAYGGGRBGCASCAG
    
    CTGSTGCVYCCCRTAGG

本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-08-10 11:56 AM
