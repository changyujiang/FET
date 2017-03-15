# 前端学习笔记(1) HTML Essentials
@(Evernote)[HTML]

[TOC]

##Content Model Understanding 内容模式理解

### Content Model Intro
> These(Content model) defines the type of content expected inside an element and control syntax rules such as element nesting.

Content model 定义了element中内容的种类并控制element的句法规则，比如说嵌套。

###HTML5之前
几乎所有的HTML element 都归属于至少一种Content model。在H5之前，仅有block, inline两种：
- **block level elements** 他们自己独立成行
- **inline level elements** 一般是出现于其他内容中间

### HTML5之后
H5之后共有七种content model: **Flow, Metadata, Embedded, Interactive, Heading, Pharsing, and Sectioning.**
block 和 inline 的功能被整合在新的content model中，其中的一些表现为block level，另一些表现为inline level。

各类说明详见W3C的[document](https://www.w3.org/TR/html5/dom.html#content-models")。


##Formatting Page Content
HTML4标准因为CSS的使用，有了将所有描述性（presentational）标记移除的策略，曾将`<b><i>`等描述性标记移除，使用CSS来实现他们。相应的HTML4加入了一些逻辑性标记（logical tag）语义性（semantic）标记如`<em><strong>`。其中，`<i>`(italicized) 和`<em>`(emphasis) 的默认渲染是一样的,但是`<i>`仅仅只是告诉浏览器倾斜字体，只是视觉上的表现，而`<em>`则带有语义。同样的还有`<b>`(bold)和 `<strong>`(strong emphasis)。当然视觉上来说他们没有什么差别，但是对于机器，语义与逻辑信息更有意义。比如说machine reader，当他们阅读一段文字时就可以在有`<em>`的地方重读但却会忽略`<i>`。**所以当我们选择使用HTML标签时，要从逻辑和语义角度考虑而不是视觉的角度，把视觉部分的都交给CSS**。

### Headings

> Heading 标题标记`<h1>~<h6>`用来构建页面的**结构**，决定内容的层级。

使用heading的原则：基于他们的层级本身，基于内容的层次，重要性，而不是浏览器展现他们的大小。
使用heading的建议：
- 限制`<h1>`的数量，符合逻辑
- 顺序使用`<h1>~<h6>`，为了更清晰的结构。

### Paragraph
`<p></p>`
错误用法：使用空的段来控制行距 `<p>&nbsp;</p>`

`<br>` 
line break tag, used for hard return; no closing tag required
换行符，作为段内的换行（如一串地址），不需要结束标签。XHTML中需要`<br/>`。

###Emphasizing text
无语义的：`<i></i>` `<b></b>`
有语义的：`<em></em> <strong></strong>`

###Named character entity 字符实体
需要显示一些特殊符号或者html保留符号的时候，需要用到named character entity。
`&amp;` &
`&lang;` <
`&copy;` © copyright
[Wikipedia 完整LIST](http://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references)

`&nbsp;` non-breaking space 不间断空格
通常被用来控制单词间的空格数量，但这是不妥的做法。它的本身的任务是置于不希望被截断的单词之间，比如`Formula One`两个单词之间有空格，当页面缩放时，两个单词可能被截断在两行，这是如果用`&nbsp`来取代空格，如`Formula&nbsp;One`，就不会存在问题了。

###Image
`<img src='yourpath' alt='alternative text'>`

##Structuring Content 组织内容

通过Sectioning element，Semantic element 来组织页面的内容，层次。
- Sectioning element: `<h1>..<h6> <article> <aside> <nav> <section>`
- Semantic element: `<head> <main> <footer>`
also
powerful `<div>` tag  for grouping content
很好得运用它们可以为页面提供一个清晰的结构，使页面对于机器（搜索引擎等）和人都易读的。

就而言，我按照自己的理解采用下面的结构
![Alt text](./1489535694370.png)

