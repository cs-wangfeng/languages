# [HTML5语言入门](https://www.w3school.com.cn/html/html5_intro.asp)

## 简介

HTML5相对于HTML语言添加了很多新属性

因此先学习HTML

> 几种语言的关系：按照网友的话，HTML是骨架，CSS是皮肤，JS是肌肉🧐

第一个HTML程序：
```html5
<!DOCTYPE html>
<html>
<body>

<video width="420" controls>
  <source src="mov_bbb.mp4" type="video/mp4">
  <source src="mov_bbb.ogg" type="video/ogg">
 Your browser does not support the video tag.
</video>

</body>
</html>
```

HTML: Hyper Text Markup Language  
称为超文本标记语言

> 标记语言是一套标记标签（Markup Tag）

### 标记标签

标记标签是一种由尖括号包围的关键词，比如`<html>`

HTML标签通常是成对出现的，比如 `<b>` 和 `</b>`

### HTML文档 = 网页

HTML文档**描述网页**  

HTML文档包含
- HTML标签
- 纯文本

> web浏览器作用：读取HTML文档，以网页的形式显现出来

标签举例：

- `<html>`与`</html>`之间的文本描述网页
- `<body>`与`</body>`之间的文本是**可见的**页面内容
- `<h1>`与`</h1>`之间表示标题
- `<p>`与`</p>`之间表示为段落

## [HTML编辑器](https://www.w3school.com.cn/html/html_editors.asp)

使用记事本即可

## 基本的HTML标签 

### HTML标题/段落/链接

实例：

#### HTML标题

[标题](https://www.w3school.com.cn/tiy/t.asp?f=eg_html_headers)

```html
<h1>标题1</h1>
<h2>标题2</h2>
<h3>标题3</h3>
```

#### HTML段落

[段落](https://www.w3school.com.cn/tiy/t.asp?f=eg_html_paragraphs1)

```html
<p>这是段落。</p>
<p>这是段落。</p>
<p>这是段落。</p>

<p>段落元素由 p 标签定义。</p> 
```

#### HTML网络链接

```html
<a href="http://www.w3school.com.cn">
This is a link</a>
```

> html使用`<a>...</a>`进行链接的表示，在`<a>`中的href(Hypertext REFerence)表示这个链接

#### HTML图片链接

```html
<img src = "picture.png", width = "30%", height = "30%"/>
```
示例1：

```html
<img src="https://user-images.githubusercontent.com/83827774/178895836-6ec93f6d-726a-4182-93ef-375e42b98cdf.png" width="20%" height="20%" />
```


显示结果：

<img src="https://user-images.githubusercontent.com/83827774/178895836-6ec93f6d-726a-4182-93ef-375e42b98cdf.png" width="20%" height="20%" />

目前试验发现，最后面的`/>`的貌似没有`/`也可以  
个人理解是为了保持每个元素都是关闭的，也就是`/`是关闭的意思  
但是大多浏览器可以默认你的意思是最后有`/>`来作为关闭标签

例如(下面空元素的讲解)：

> 没有内容的 HTML 元素被称为空元素。空元素是在开始标签中关闭的。  
> `<br>` 就是没有关闭标签的空元素（`<br>` 标签定义换行）。  
在 XHTML、XML 以及未来版本的 HTML 中，所有元素都必须被关闭。  
在开始标签中添加斜杠，比如 `<br />`，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。  
即使 `<br>` 在所有浏览器中都是有效的，但使用 `<br />` 其实是更长远的保障。  

示例2：

图片超链接

```html
<a href = "https://www.baidu.com"><img src="https://user-images.githubusercontent.com/83827774/178895836-6ec93f6d-726a-4182-93ef-375e42b98cdf.png" width="20%" height="20%" /></a>
```

显示结果：

<a href = "https://www.baidu.com"><img src="https://user-images.githubusercontent.com/83827774/178895836-6ec93f6d-726a-4182-93ef-375e42b98cdf.png" width="20%" height="20%" /></a>
> 注：此时点击图片可以进入百度界面

**图像的大小，既可以使用百分数比例，也可以使用数字直接进行大小的规定**

## HTML元素

HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

P.S. 开始标签常被称为开放标签（opening tag），结束标签常称为闭合标签（closing tag）。

元素 = 开始标签 + 内容 + 结束标签

元素举例：
- `<p>`元素
- `<body>`元素
- `<html>`元素
    
*即使您忘记了使用结束标签，大多数浏览器也会正确地显示 HTML，但是不要依赖于此*

---
例如

```html
<p>This is a paragraph
<p>This is a paragraph
```
上面的代码在这个.md中使用之后，后面的回车到下一行的时候，都会出现自动行首流出两个空格的问题，因此就不展示了

---
  
### 空元素
  
没有内容的 HTML 元素被称为空元素。空元素是在开始标签中关闭的。  
  
`<br/>`的意思是Line Break Element  
  
`<br>` 就是没有关闭标签的空元素（`<br>` 标签定义换行）。  
  
在 XHTML、XML 以及未来版本的 HTML 中，所有元素都必须被关闭。  
  
在开始标签中添加斜杠，比如 `<br />`，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。  
  
即使 `<br>` 在所有浏览器中都是有效的，但使用 `<br />` 其实是更长远的保障。 
  
> 注：元素标签的大小写问题  
HTML 标签对大小写不敏感：`<P>` 等同于 `<p>`。许多网站都使用大写的 HTML 标签。  
万维网联盟（W3C）在 HTML 4 中推荐使用小写，而在未来 (X)HTML 版本中强制使用小写。
  
## HTML属性
HTML 标签可以拥有属性。属性提供了有关 HTML 元素的更多的信息。

名称/值对：name = value
  
属性总是在 HTML 元素的开始标签中规定。
  
例如：
```html
<a href="http://www.w3school.com.cn">This is a link</a>
```

**更多属性：**

(1)居中排列标题：

```html
<h2 align = "center">居中排列标题</h2>
```

展示：  

<h2 align = "center">居中排列标题</h2>

(2)文档主题背景颜色：  

```html
<body bgcolor = "green">
绿色背景
</body>
```

示例：

代码：

```html
<!DOCTYPE html>
<html>
<body bgcolor = "green">
<h1 align = "center">这是标题</h1>

<p align = "center">这是段落</p>
<p>这是段落</p>
哈哈<br/>
<br/>
<a href = "https://www.baidu.com"><img src="https://user-images.githubusercontent.com/83827774/178894842-5ce4d4f9-f3d8-41c5-be33-3ac80a2af16b.png" width="10%" height="10%" /></a>


</body>
</html>
```

网页中展示：

<img width="1080" alt="image" src="https://user-images.githubusercontent.com/83827774/178903741-eff433d9-1142-4259-89f6-c5238d335799.png">

(3)表格属性：

`<table>` 定义 HTML 表格。  

`<table border="1">` 拥有关于表格边框的附加信息。

<br/><br/>
---

> HTML 提示：使用小写属性  
属性和属性值对大小写不敏感。   
不过，万维网联盟在其 HTML 4 推荐标准中推荐小写的属性/属性值。  
而新版本的 (X)HTML 要求使用小写属性。  

> 始终为属性值加引号  
属性值应该始终被包括在引号内。双引号是最常用的，不过使用单引号也没有问题。  
在某些个别的情况下，比如属性值本身就含有双引号，那么您必须使用单引号.

例如：  
```html
name='Bill "HelloWorld" Gates'
```

## HTML标题

标题的定义范围：`<h1>`到`<h6>`

浏览器会自动在标题前后加上空行  
默认情况下，HTML 会自动地在块级元素前后添加一个额外的空行，比如段落、标题元素前后。

## HTML水平线(horizontal rule)

`<hr/>`，类似于markdown中的`---`

提示：使用水平线 (<hr> 标签) 来分隔文章中的小节是一个办法（但并不是唯一的办法）。

## HTML注释
```
<!--这是注释-->
```
## HTML的style属性

## HTML引用

这两块写过了,没有commit,结果不小心点击了issues,全都丢失了,心态崩溃...

## [HTML颜色表](https://www.w3school.com.cn/html/html_colors.asp) [HTML颜色名](https://www.w3school.com.cn/html/html_colornames.asp)

## HTML CSS

CSS的含义：Cascading Style Sheet （层叠样式表）

通过使用 HTML4.0，所有的格式化代码均可移出 HTML 文档，然后移入一个独立的样式表。

<b>如何使用样式</b>

当浏览器读到一个样式表，它就会按照这个样式表来对文档进行格式化。有以下三种方式来插入样式表：

- 外部样式表   
当样式需要被应用到很多页面的时候，外部样式表将是理想的选择。使用外部样式表，你就可以通过更改一个文件来改变整个站点的外观。<br/>
```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

- 内部样式表  
当单个文件需要特别样式时，就可以使用内部样式表。你可以在 head 部分通过`<style>`标签定义内部样式表。
```html
<head>

<style type="text/css">
body {background-color: red}
p {margin-left: 20px}
</style>
</head>
```

- 内联模式






