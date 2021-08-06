---
layout: post
title: markdown教程
categories: markdown
description: markdown教程
keywords: markdown, 教程
---

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。  
Markdown 语言在 2004 由约翰·格鲁伯（英语：John Gruber）创建。  
Markdown 编写的文档可以导出 HTML 、Word、图像、PDF、Epub 等多种格式的文档。  
Markdown 编写的文档后缀为 .md, .markdown。

# Markdown 标题

Markdown 标题格式
使用 # 号可表示 1-6 级标题，一级标题对应一个 # 号，二级标题对应两个 # 号，以此类推。
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

段落的换行是使用两个以上空格加上回车

\*斜体文本\*
*斜体文本*
\*\*粗体文本\*\*
**粗体文本**
\*\*\*粗斜体文本\*\*\*
***粗斜体文本***

分割线 ---
- - -  
~~删除线~~  
<u>带下划线文本</u>  
创建脚注格式类似这样 [^注解]。
[^注解]: 这是一个注解

无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容：
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项

有序列表使用数字并加上 . 号来表示，如：
1. 第一项
2. 第二项
3. 第三项

列表嵌套只需在子列表中的选项前面添加四个空格即可：
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素

Markdown 区块引用是在段落开头使用 > 符号 ，然后后面紧跟一个空格符号
> 区块引用 
> 菜鸟教程 
> 学的不仅是技术更是梦想 

另外区块是可以嵌套的，一个 > 符号是最外层，两个 > 符号是第一层嵌套，以此类推：
> 最外层
> > 第一层嵌套
> > > 第二层嵌套

区块中使用列表实例如下：
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项

如果是段落上的一个函数或片段的代码可以用反引号把它包起来（`），例如：
`printf()` 函数

可以用 ``` 包裹一段代码，并指定一种语言（也可以不指定）：
```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```

链接使用方法如下：  
这是一个链接 [海贼王](https://www.shiqiang.space)

Markdown 图片语法格式如下：
![海贼王](https://panlongshouhu.github.io/shiqiang/assets/images/qrcode.png)  
![海贼王](https://panlongshouhu.github.io/shiqiang/assets/images/qrcode.png "海贼王")

当然，你也可以像网址那样对图片网址使用变量:
这个链接用 1 作为网址变量 [海贼王][icon].
然后在文档的结尾为变量赋值（网址）
[icon]: https://panlongshouhu.github.io/shiqiang/assets/images/qrcode.png

Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 <img> 标签。
<img src="https://panlongshouhu.github.io/shiqiang/assets/images/qrcode.png" width="50%">

Markdown 制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。
语法格式如下：

|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |

我们可以设置表格的对齐方式：

-: 设置内容和标题栏居右对齐。
:- 设置内容和标题栏居左对齐。
:-: 设置内容和标题栏居中对齐。

支持的 HTML 元素
不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。

目前支持的 HTML 元素有：<kbd> <b> <i> <em> <sup> <sub> <br>等 ，如：
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑

Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符，Markdown 使用反斜杠转义特殊字符：
**文本加粗** 
\*\* 正常显示星号 \*\*