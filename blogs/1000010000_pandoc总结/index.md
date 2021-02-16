最近想把markdown文档拿到电子书上看，用了pandoc这个神器做格式转换，总结几条命令参数。以后用到pandoc的命令总结都添加在这里。
* `-o` 定义输出文件,而非标准输出。
* `-S`或`–smart` 创建印刷版的输出。
* `-s`或`–standalone` 输出一个独立文档，而不是输出没有头部和尾部的文档片段。
* `-V KEY[=VAL]`或`–variable=KEY[:VAL]` 设置模板变量。
* `–toc`或`–table-of-contents` 在输出文档中包含自动生成的内容表格。
* `–latex-engine=pdflatex|lualatex|xelatex` 当创建pdf输出时，选择适当的LaTeX引擎。
* `-N`或`–number-sections` 标号章节头。