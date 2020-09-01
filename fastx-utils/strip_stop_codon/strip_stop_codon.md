# fastx-utils之去除序列末端的终止密码子：strip_stop_codon

### 一、fastx-utils strip_stop_codon介绍

**功能描述：**

`fastx-utils strip_stop_codon`去除序列末端的终止密码子。

**命令行接口：**

    $ fastx-utils strip_stop_codon
    
    Usage: fastx-utils strip_stop_codon <fasta>

### 二、使用场景实例及其用法

**使用场景经典案例：**

1. 一些程序输入文件需要去除终止密码,比如`Interproscan`.

**示例演示：**

**示例文件：** `transdecode.faa`

    $ cat transdecode.faa | head -n  7


    >TCU_g100011_i1.p1
    GLQNVVCIGVQAVRKETMAGPSLLHRHDTSLVKTLSFFTYPHYRIYVFPAQIIFFNCPHF
    RHIFSALNAQKNIQNEQSLSCSNVFFFFGRHLVFTSPHVSTPQI*
    >TCU_g10001_i1.p1
    KKYGGNLDWKFGDMPVLEPNLANALRWKEDVRDANGNRTLPIGPIKWQYDDDGDLVAIAI
    GSEKGSPRNKVLAGLHPEEGVTRLALSPGRQTTPHQALFATASRTGAETLHQSTTKAPEN
    DATFPNANGSIHPISTTSP

**运行命令：** 去除`transdecode.faa`序列的终止密码子。


    $ fastx-utils  strip_stop_codon transdecode.faa | head -n 6


    >TCU_g100011_i1.p1
    GLQNVVCIGVQAVRKETMAGPSLLHRHDTSLVKTLSFFTYPHYRIYVFPAQIIFFNCPHFRHIFSALNAQKNIQNEQSLSCSNVFFFFGRHLVFTSPHVSTPQI
    >TCU_g10001_i1.p1
    KKYGGNLDWKFGDMPVLEPNLANALRWKEDVRDANGNRTLPIGPIKWQYDDDGDLVAIAIGSEKGSPRNKVLAGLHPEEGVTRLALSPGRQTTPHQALFATASRTGAETLHQSTTKAPENDATFPNANGSIHPISTTSP
    >TCU_g100025_i1.p1
    SFYCFNALGSSRRHRIGPLNLPSCPQWYWICPNLHSPSSALLSLWRRLIFLVVKKHCSPALQSIDCFFRCPALLLLFSVYADCSGGHANAHGKDGINCP


本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-08-10 11:56 AM
