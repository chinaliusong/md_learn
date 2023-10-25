---
linkReferences: true
title: markdown使用笔记
---
# markdown规则
## 正常文字

测试文字

## 加粗

**测试文字**

## 斜体

*测试文字*

## 表格
### 常规表格

| First Header                | Second Header                |
| --------------------------- | ---------------------------- |
| Content from cell 1         | Content from cell 2          |
| Content in the first column | Content in the second column |

### 合并单元格（NO）
#### 左右合并

|  a  |  b  |
| :-: | :-: |
|  >  |  1  |
|  2  |     |
|算法

#### 上下合并

| a   | b   |
| --- | --- |
| 1   | 2   |
| ^   | 4   |


## 网址引用
[GitHub](https://github.com)

## 引用

> 测试
>> 测试(NO)

## 待办
- [ ] TODO
- [x] DONE

## 脚注
说明[^1]

[^1]: 脚注

## 代码
`<addr>`

or

```C++
std::vector<std::string> array;
std::vector<std::string>::iterator it = array.begin();
// auto
auto it = array.begin();
```

## 告警(NO)
!!! waring test title
    warning test notes
    
## 数学公式
$f(x) = sin(x)+12$

## 交叉引用
### 图交叉引用
#### 单图交叉引用
![引用测试图](../../DrawBed/learn/markdown/引用测试图.png){#fig-id}

详情见[@fig:id]

#### 双图交叉引用
<div id="fig:figureRef">

![测试图1](../../DrawBed/learn/markdown/引用测试图.png){#fig:figureRefA}

![测试图2](../../DrawBed/learn/markdown/引用测试图.png){#fig:figureRefB}

总图名

</div>

总图引用详情见[@fig:figureRef]

分图1引用详情见[@fig:figureRefA]

分图2引用详情见[@fig:figureRefB]

#### 四图交叉引用

<div id="fig:coolFig">
![caption a](../DrawBed/learn/markdown/引用测试图.png){#fig:cfa width=30%}
![caption b](../DrawBed/learn/markdown/引用测试图.png){#fig:cfb width=60%}
![caption c](../DrawBed/learn/markdown/引用测试图.png){#fig:cfc width=10%}

![caption d](../DrawBed/learn/markdown/引用测试图.png){#fig:cfd}

![caption e](../DrawBed/learn/markdown/引用测试图.png){#fig:cfe}

![caption f](../DrawBed/learn/markdown/引用测试图.png){#fig:cff}

Cool figure!
</div>

### 表交叉引用

| 序号 | 名称              | 备注         |
| ---- | ----------------- | ------------ |
| 1    | SvcNetReceive.exe | 接收测试软件 |
| 2    | SvcNetSend.exe    | 发送测试软件 |
| 3    | wireshark         | 抓包软件     |
|||
Quarto 文章正文的默认宽度约为 700 像素。 这通常会在文档页边距中留下一些可用空间，读者可以通过多种方式利用该空间。

我们可以使用 `column: page-right` 选项来指示所需图形占据屏幕的整个宽度，并加入一些图形。例如，以下代码并排加入了两个图形。

```text
#| label: fig-histogram
#| fig-cap: "Histograms of individual variables"
#| fig-subcap:
#|   - "Histogram of `price`s"
#|   - "Histogram of `area`s" 
#| layout-ncol: 2
#| column: page-right
```

: tableName {#tbl:label}

详情见[@tbl:label]

### 公式引用

$$ math $$ {#eq:q1}

详情见[@eq:q1]

### 参考文献引用

参考文献示例[@陈秀梅2001对类风湿关节炎病人性格的调查分析]