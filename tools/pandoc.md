
# pandoc使用说明
## word
### word命令解析
``` shell
pandoc --citeproc --number-sections \
--csl china-national-standard-gb-t-7714-2015-author-date.csl \
--bibliography ref.bib -M reference-section-title="参考文献" \
-M link-citations=true --reference-doc ref.docx input.md -o main.docx
```

**pandoc：执行 Pandoc 命令**
•	--citeproc：处理文献引用，也可用 -C 代替
•	--number-sections：对各级标题编号，形如 1, 1.1, 1.1.1，也可用 -N 代替
•	--csl china-national-standard-gb-t-7714-2015-author-date.csl：指定参考文献样式，这里使用的是 GB/T 7714-2015 的著者-出版年制格式，更多样式可以前往 Zotero Style Repository 下载
•	--bibliography ref.bib：引文数据文件，即前文由 Better BibTeX for Zotero 导出的 ref.bib
•	-M reference-section-title="参考文献"：设置参考文献表的标题为「参考文献」，不编号
•	-M link-citations=true：设置正文引用可以超链接到参考文献表中相应的条目，默认为 false
•	--reference-doc ref.docx：参考的 DOCX 文件格式，根据 Pandoc 使用手册，最好的方式是通过命令 pandoc -o custom-reference.docx --print-default-data-file reference.docx 得到 Pandoc 的默认 DOCX 文件，然后用 Microsoft Word 打开这个文件，根据你的喜好进行修改
•	input.md：存储文章内容的 Markdown 文件
•	-o main.docx：输出 DOCX 文件
•	\：反斜杠，表示换行，你也可以删除它，把所有命令写在一行。

### word增加title
```yaml
--- 
title: "56所加解密设备测试报告"
author: 刘松
date: "2023-09-23"
subject: "Markdown"
keywords: [test]
---
```
### 生成word文档示例
```shell
pandoc --filter pandoc-crossref -M chapters -M figureTitle="图" -M figPrefix="图" -M tableTitle="表" -M tblPrefix="表" --citeproc -M reference-section-title="参考文献" --csl=../Standard/china-national-standard-gb-t-7714-2015-author-date.csl --bibliography=../Standard/ref.bib -M link-citations=true --reference-doc=../Standard/templates_refine.docx paper.md -o paper.docx
```
#### 解析
##### 基础命令
```pandoc paper.md -o paper.docx```
##### 交叉引用
```--filter pandoc-crossref -M chapters -M figureTitle="图" -M figPrefix="图" -M tableTitle="表" -M tblPrefix="表"```
##### 参考文献
```--citeproc -M reference-section-title="参考文献" --csl=../Standard/china-national-standard-gb-t-7714-2015-author-date.csl --bibliography=../Standard/ref.bib -M link-citations=true```
##### 参考文档
```--reference-doc=../Standard/templates_refine.docx```
