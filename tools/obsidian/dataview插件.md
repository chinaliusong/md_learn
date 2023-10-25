# dataview插件

## dataview 元素
- `filename` 文件标题
- `file.folder`
- `file.path`
- `file.link`
- `file.size`
- `file.ctime`
- `file.cday`
- `file.mtime`
- `file.mday`
- `file.tags`
- `file.inlinks`
- `file.outlinks`
- `file.aliases`

## 示例
```dataview
list 
from "dir"
where
contains(file.name,"dataview")
sort file.ctime
```
> list 展现形式，table、task可选
> from 检索范围，从那个文件夹“dir”
> where 条件
> sort 排序，sort file.ctime根据文件的创建时间正序

```dataview
list
from ""
where contains(file.name,"git")
```
> from "" 不筛选文件夹和标签，从所有笔记中查找

```dataview
list
from #computer 
```