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

<a href = "www.baidu.com"><img src="https://user-images.githubusercontent.com/83827774/178894842-5ce4d4f9-f3d8-41c5-be33-3ac80a2af16b.png" width="10%" height="10%" /></a>
