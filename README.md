# biostack-suits-docs: Docs for tools in biostack-suits 


1. 命令行工具介绍

```
    tsv-utils  cut         -d -f2,3             zotu_table.txt  >   zotu_table.subset.txt
    |          |           |  |                 |               |   |
    |          Subcommand  |  Parameter option  |               |   Output filename
    Binary file            Parameter option     Input file      Redirect stdout 
```

命令行程序主要有几部分组成:

```
Binary file              可执行文件
Subcommand               子命令(可选)
Parameter option         参数选项
Input file               输入文件
Redirect output          输出重定向符号
Output filename          输入文件列表
```

`注意事项:` 注意保留不同组成部分之间的空格。

2. [tsv-utils](tsv-utils/tsv-utils.md)： tools for manipulate tsv files.

3. [fastx-utils](fastx-utils/fastx-utils.md)： tools for manipulate fasta/q files.
