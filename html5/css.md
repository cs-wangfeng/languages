# [CSS教程](https://www.w3schools.com/css/default.asp)

## CSS简介

CSS is the language we use to _**style**_ an HTML document.

CSS describes how HTML elements should be displayed.

What is CSS?  
> CSS stands for Cascading Style Sheets  
CSS describes how HTML elements are to be displayed on screen, paper, or in other media  
CSS saves a lot of work. It can control the layout of multiple web pages all at once  
External stylesheets are stored in CSS files    


举个例子：
```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: lightblue;
}

h1 {
  color: white;
  text-align: center;
}

p {
  font-family: verdana;
  font-size: 20px;
}
</style>
</head>
<body>

<h1>My First CSS Example</h1>
<p>This is a paragraph.</p>

</body>
</html>
```
CSS 用于定义网页样式，包括针对不同设备和屏幕尺寸的设计、布局和显示变化。  

The style definitions are normally saved in external .css files.

我们只需要这个 `external stylesheet file` 即可改变外观

## CSS Syntax

A CSS rule consists of a `selector` and a `declaration block` .

<img src = "https://www.w3schools.com/css/img_selector.gif" width= "70%"/>

举个例子：
```html
<!DOCTYPE html>
<html>
<head>
<style>
p {
  color: red;
  text-align: center;
  font-family: consolas;
  font-size: 20px;
} 
</style>
</head>
<body>

<p>Hello World!</p>
<p>These paragraphs are styled with CSS.</p>

</body>
</html>
```
显示效果：

<img src="https://user-images.githubusercontent.com/83827774/179882092-3b03b2a2-d592-4a1c-8253-e23a42e269cf.png"/>

## CSS selectors

A CSS selector selects the HTML element(s) you want to style.

CSS选择器有以下五种：
- Simple selectors (select elements based on name, id, class)
- Combinator selectors (select elements based on a specific relationship between them)
- Pseudo-class selectors (select elements based on a certain state)
- Pseudo-elements selectors (select and style a part of an element)
- Attribute selectors (select elements based on an attribute or attribute value)


### CSS element selector
```html
p {
  text-align: center;
  color: red;
}
```

### CSS id selector

一个元素的 id 在一个页面中是唯一的，所以 id 选择器用于选择一个唯一的元素

要选择具有特定 id 的元素，请编写一个井号 (#) 字符，后跟该元素的 id

id选择器定义方法：

```html
#para1 {
  text-align: center;
  color: red;
}
```

> 注：**An id name cannot start with a number!**

举例：

```html
<!DOCTYPE html>
<html>
<head>
<style>
#para1 {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<h1 id="para1">hhhh</h1>

<p id="para1">Hello World!</p>
<p>This paragraph is not affected by the style.</p>

</body>
</html>
```
效果：

![image](https://user-images.githubusercontent.com/83827774/179884639-96b7c669-8b1d-4f91-a827-4be079058062.png)

相对比的，如果没有这个id定义的话：

![image](https://user-images.githubusercontent.com/83827774/179885062-7f52f38c-f6e1-4c2b-91b4-0892c16b3493.png)

### CSS class selectors

The class selector selects HTML elements with a specific class attribute.

To select elements with a specific class, write a period (.) character, followed by the class name.

```html
<!DOCTYPE html>
<html>
<head>
<style>
.center {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<h1 class="center">Red and center-aligned heading</h1>
<p class="center">Red and center-aligned paragraph.</p> 

</body>
</html>
```
这样定义之后，很多类别的元素都可以属于这个类之中

还可以定义特定的类别元素才能属于这个类

（You can also specify that only specific HTML elements should be affected by a class.）
```html
<!DOCTYPE html>
<html>
<head>
<style>
p.center {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<h1 class="center">This heading will not be affected</h1>
<p class="center">This paragraph will be red and center-aligned.</p> 

</body>
</html>
```

**HTML 元素也可以引用多个类。**

```html
<!DOCTYPE html>
<html>
<head>
<style>
p.center {
  text-align: center;
  color: red;
}

p.large {
  font-size: 300%;
}
</style>
</head>
<body>

<h1 class="center">This heading will not be affected</h1>
<p class="center">This paragraph will be red and center-aligned.</p>
<p class="center large">This paragraph will be red, center-aligned, and in a large font-size.</p> 

</body>
</html>
```

注意：A class name cannot start with a number!

### CSS Universial selectors

`*`表示 selector 选择页面上的所有 HTML 元素

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  text-align: center;
  color: blue;
}
</style>
</head>
<body>

<h1>Hello world!</h1>

<p>Every element on the page will be affected by the style.</p>
<p id="para1">Me too!</p>
<p>And me!</p>
<br/>
poo

</body>
</html>
```

### CSS Grouping selector

将style定义相同的放在一起定义即可

例如：

```html
h1 {
  text-align: center;
  color: red;
}

h2 {
  text-align: center;
  color: red;
}

p {
  text-align: center;
  color: red;
}
```

可以修改成：

```html
h1, h2, p {
  text-align: center;
  color: red;
}
```
总结：

![image](https://user-images.githubusercontent.com/83827774/179891874-0d74bd0c-81c0-454b-81ed-778c5aae6030.png)

## How to add CSS

### 3 ways to add CSS

- External CSS
- Internal CSS
- Inline CSS

### Externel CSS

Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section.

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

`.css` 文件 `mystyle.css` ：

```html
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```
注意这种 `20px` 的数字加单位的写法不能在二者之间加上空格，也就是说 `20 px` 是错误的

### Internal CSS

如果单个 HTML 页面具有独特的样式，则可以使用内部样式表。

内部样式在 `<style>` 元素内定义，在 `<head>` 部分内。(就像之前的那个)

举个例子：
```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```
### Inline CSS

内联样式可用于为单个元素应用独特的样式。

要使用内联样式，请将 style 属性添加到相关元素。 style 属性可以包含任何 CSS 属性。

例如：

```html
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

### 注意事项：Multiple Style Sheets

会按照最后面的一种定义方式的 style sheet 进行对于样式的约定


## CSS comments

A CSS comment is placed inside the `<style>` element, and starts with `/*` and ends with `*/`

但是HTML的comment还是 `<!-- xxx -->`

## CSS color

区分背景的颜色以及文字的颜色

背景的颜色：`<h1 style="background-color:DodgerBlue;">Hello World</h1>`

文字的颜色：`<h1 style="color:Tomato;">Hello World</h1>`

边缘的颜色：`<h1 style="border:2px solid Tomato;">Hello World</h1>`    
效果示例：  
![image](https://user-images.githubusercontent.com/83827774/180021896-6ec5e7fe-1584-4668-a577-4e2e4eb94574.png)

### 颜色表示方式

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>
```
三种表示番茄红的颜色方式

```html
<h1 style="background-color:rgba(255, 99, 71, 0.5);">...</h1>
<h1 style="background-color:hsla(9, 100%, 64%, 0.5);">...</h1>
```
这种的带 `a` 的表示方法是加了一个透明度参数，也就是括号里面最后一个参数0.5，意思是透明度为50%

### 表示方式1 - rgb

rgb(red, green, blue)

[**rgb颜色混合器**](https://www.w3schools.com/css/css_colors_rgb.asp)  

拓展方式：rgba

rgba(red, green, blue, alpha)

### 表示方式2 - hex

相当于16进制的rgb表示方式  

`#RRGGBB`

* 简写方式：
```html
body {
  background-color: #fc9; /* same as #ffcc99 */
}

h1 {
  color: #f0f; /* same as #ff00ff */
}

p {
  color: #b58; /* same as #bb5588 */
}
```

### 表示方式3 - hsl

hsl(hue, saturation, lightness)

拓展方式：hsla

## CSS background

- background-color
- background-image  
```html
p {
  background-image: url("paper.gif");
}
```
- background-repeat  
表示图像是否重复以及图像位置的属性，详情：https://www.w3schools.com/cssref/pr_background-position.asp  
- background-attachment  
这个属性会指定背景是滚动（scroll）还是固定（fixed）  
```html
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: scroll;/*或者是fixed*/
}
```
类似这种定义方式，但是我看默认是scroll
- background-shorthand  
可以说是一种快速定义background属性的方法，例如：  
```html
body {
  background: #ffffff url("img_tree.png") no-repeat right top;
}
```
按照如下的顺序定义：`background-color`, `background-image`, `background-repeat`, `background-attachment`, `background-position`    
是否缺少其中一个属性值并不重要，只要其他属性值按此顺序排列即可。  
- background-origin  
可以确定背景图片放置的位置  

## CSS borders  

shorthand:  
```html
p {
  border: 5px solid red;
}
```
or
```html
p {
  border-left: 5px solid red;
}
```
```html
p {
  border: 2px solid red;
  border-radius: 5px;
}
```
`border-radius` 可以用于调节边框角的圆弧半径  

## CSS margin & padding

`margin` 用于控制某个元素四周的空白大小 - border外面  

相对比的：  
`padding` 是在border里面的空白大小  

CSS has properties for specifying the padding for each side of an element:

- padding-top
- padding-right
- padding-bottom
- padding-left

Padding - Shorthand Property  
- padding-top
- padding-right
- padding-bottom
- padding-left

## CSS Box Model

<img src="https://user-images.githubusercontent.com/83827774/180139746-bcc419c9-6a82-46d0-9b35-1125b25155a6.png" width=60%/>

## CSS outline

outline properties:
- outline-style:  
具体style可见：https://www.w3schools.com/css/css_outline.asp  
举例：
```html
p.dotted {outline-style: dotted;}
p.dashed {outline-style: dashed;}
p.solid {outline-style: solid;}
p.double {outline-style: double;}
p.groove {outline-style: groove;}
p.ridge {outline-style: ridge;}
p.inset {outline-style: inset;}
p.outset {outline-style: outset;}
```
- outline-color
- outline-width
- outline-offset
- outline(shorthand)    
The outline property is a shorthand property for setting the following individual outline properties:  
  - outline-width  
  - outline-style (required)  
  - outline-color   
- outline offset  
outline-offset 属性在轮廓和元素的边缘/边框之间添加空间。元素与其轮廓之间的空间是透明的。  
example:  
```html
<!DOCTYPE html>
<html>
<head>
<style>
p {
  margin: 30px;
  border: 1px solid black;
  outline: 1px solid red;
  outline-offset: 5px;
}
</style>
</head>
<body>

<h2>The outline-offset Property</h2>

<p>This paragraph has an outline 15px outside the border edge.</p>

</body>
</html>
```
形成效果：  
![image](https://user-images.githubusercontent.com/83827774/180141330-e880fa0e-fa54-402a-a296-0ecb18ffe665.png)

## CSS text

### text color

color属性专指text的颜色：

举例

```html
body {
  background-color: lightgrey;
  color: blue;
}

h1 {
  background-color: black;
  color: white;
}

div {
  background-color: blue;
  color: white;
}
```

### text alignment

`text-align` is used to set the horizontal alignment of a text.

![image](https://user-images.githubusercontent.com/83827774/180144763-666e02cb-5205-4eaa-9192-cac950b3d127.png)


### text decoration
_**（实际上是文本装饰线）**_

#### text-decoration-line

text-decoration-line 属性用于向文本添加装饰线。  

示例：  
```html
h1 {
  text-decoration: overline;
}

h2 {
  text-decoration: line-through;
}

h3 {
  text-decoration: underline;
}

p.ex {
  text-decoration: overline underline;
}
```
`text-decoration-color` 这个属性是在定义**文本装饰线的颜色**  

#### text-decoration-style

定义文本装饰线的样式

#### text-decoration-thickness
定义文本装饰线的粗细

#### text-decoration shorthand property

The `text-decoration` property is a shorthand property for:

- text-decoration-line (required)
- text-decoration-color (optional)
- text-decoration-style (optional)
- text-decoration-thickness (optional)

example:

```html
<!DOCTYPE html>
<html>
<head>
<style>
h1 {
  text-decoration: underline;
}

h2 {
  text-decoration: underline red;
}

h3 {
  text-decoration: underline red double;
}

p {
  text-decoration: underline red double 5px;
}
</style>
</head>
<body>

<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<p>A paragraph.</p>

</body>
</html>
```

**small tip:**  
默认情况下，HTML 中的所有链接都带有下划线。有时您会看到链接的样式没有下划线，具体的实现方法如下：

```html
/*在定义中使用这样的样式：*/
<head>
<style>
a {
  text-decoration: none;
}
</style>
</head>
```

## text transform  

The text-transform property is used to specify uppercase and lowercase letters in a text.

It can be used to turn everything into uppercase or lowercase letters, or capitalize the first letter of each word:

```html
p.uppercase {
  text-transform: uppercase;
}

p.lowercase {
  text-transform: lowercase;
}

p.capitalize {
  text-transform: capitalize;
}
```

<hr/>

## \*\*\*\*Initial and Inherit

example for Inherit: https://www.w3schools.com/cssref/tryit.asp?filename=trycss_inherit  

example for initial: https://www.w3schools.com/cssref/tryit.asp?filename=trycss_initial

<hr/>

## CSS text spacing properties

### text Identation  

```html
<head>
<style>
p {
  text-indent: 50px;
}
</style>
</head>
```

### letter spacing

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2 {
  letter-spacing: 5px;
}

h3 {
  letter-spacing: -2px;
}
</style>
</head>
<body>

<h1>Using letter-spacing</h1>

<h2>This is heading 1</h2>
<h3>This is heading 2</h3>

</body>
</html>
```

### line Height

```hmtl
<head>
<style>
p.small {
  line-height: 0.7;
}

p.big {
  line-height: 1.8;
}
</style>
</head>
```

### word spacing

### White Space 

white-space 属性指定如何处理元素内的空白

关于white-space的一些具体属性值（property values）

property|description 
--|--
normal|空白序列将折叠成单个空白。文本将在必要时换行。这是默认的  
nowrap|空白序列将折叠成单个空白。文本永远不会换行到下一行。文本在同一行继续，直到遇到 `<br>` 标记
pre|空白由浏览器保留。文本只会在换行符处换行。类似于 HTML 中的 `<pre>` 标签
pre-line|空白序列将折叠成单个空白。文本将在必要时或者换行符处换行
pre-wrap|空白由浏览器保留。文本将在必要时或者换行符处换行
initial|...
inherit|...

## text shadow

```html
h1 {
  text-shadow: 2px 2px 5px red; /*水平偏移，垂直偏移，模糊效果，阴影颜色*/
}
```
效果图：  
![image](https://user-images.githubusercontent.com/83827774/180156529-0d7b4fa0-ccbd-4a0c-a5c3-c68894fe5c2c.png)

※**可以有多种阴影：**
```html
<!DOCTYPE html>
<html>
<head>
<style>
h1 {
  color: white;
  text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
}
</style>
</head>
<body>

<h1>Text-shadow effect!</h1>

</body>
</html>
```
显示效果：  

<img src="https://user-images.githubusercontent.com/83827774/180157714-739d3fb3-6109-4fa1-805f-459a440740b6.png" width=30%/>

## text font

`font-family` 属性应该包含几个字体名称作为“备用”系统，以确保浏览器/操作系统之间的最大兼容性。从您想要的字体开始，以通用系列结束（如果没有其他字体可用，让浏览器在通用系列中选择类似的字体）。字体名称应以逗号分隔。

之所以使用逗号写出好多个字体，就是为了备用，因为有些浏览器不支持这些字体，就从前往后依次选择后面的备用字体

> However, there are no 100% completely web safe fonts. There is always a chance that a font is not found or is not installed properly.<br/>
Therefore, it is very important to always use fallback fonts.<br/>
This means that you should add a list of similar "backup fonts" in the font-family property. If the first font does not work, the browser will try the next one, and the next one, and so on. Always end the list with a generic font family name.

举例：
```html
<!DOCTYPE html>
<html>
<head>
<style>
.p1 {
  font-family: "Times New Roman", Times, serif;
}

.p2 {
  font-family: Arial, Helvetica, sans-serif;
}

.p3 {
  font-family: "Lucida Console", "Courier New", monospace;
}
</style>
</head>
<body>

<h1>CSS font-family</h1>
<p class="p1">This is a paragraph, shown in the Times New Roman font.</p>
<p class="p2">This is a paragraph, shown in the Arial font.</p>
<p class="p3">This is a paragraph, shown in the Lucida Console font.</p>

</body>
</html>
```

比较保险的几个字体：
<ul>
  <li>Arial (sans-serif)</li>
  <li>Verdana (sans-serif)</li>
  <li>Helvetica (sans-serif)</li>
  <li>Tahoma (sans-serif)</li>
  <li>Trebuchet MS (sans-serif)</li>
  <li>Times New Roman (serif)</li>
  <li>Georgia (serif)</li>
  <li>Garamond (serif)</li>
  <li>Courier New (monospace)</li>
  <li>Brush Script MT (cursive)</li>
</ul>


## 字体的风格属性

### font-style

主要是调整为斜体
```html
p.normal {
  font-style: normal;
}

p.italic {
  font-style: italic;
}

p.oblique {
  font-style: oblique;
}
```

### font-weight

主要是调整字体的粗细
```html
<head>
<style>
p.normal {
  font-weight: normal;
}

p.light {
  font-weight: lighter;
}

p.thick {
  font-weight: bold;
}

p.thicker {
  font-weight: 900;
}
</style>
</head>
```

### font-variant

可以调整字体为 `small-caps`

属性值：

<img src="https://user-images.githubusercontent.com/83827774/180173707-854fbdb7-77a0-47da-9367-81c9edc1dd01.png" width=70%/>

small-caps字体如下所示：

![image](https://user-images.githubusercontent.com/83827774/180173835-906f41cd-e4f4-427e-ac1a-84f1ba47fbb7.png)

## font-size

字体大小除了 `px` 即pixel表示，还可以用单位 `em` 表示，`1em = 16px`

还可以用百分数表示，也就是说字体相当于默认字体大小的百分之多少

还可以用 `vw` 表示

## [google font](https://www.w3schools.com/css/css_font_google.asp)

使用如下的 `<link>` 引入谷歌字体:
```html
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia">
<style>
body {
  font-family: "Sofia", sans-serif;
}
</style>
</head>
```

> info about link tag: https://www.w3schools.com/tags/tag_link.asp

## Font Shorthand

font shorthand的属性：   
<ul>
<li><code class="w3-codespan">font-style</code></li>
<li><code class="w3-codespan">font-variant</code></li>
<li><code class="w3-codespan">font-weight</code></li>
<li><code class="w3-codespan">font-size/line-height</code></li>
<li><code class="w3-codespan">font-family</code></li>
</ul>

使用font shorthand举例：  
```html
<head>
<style>
p.a {
  font: 20px Arial, sans-serif;
}

p.b {
  font: italic bold 12px/30px Georgia, serif;
}
</style>
</head>
```

## [CSS Icon](https://www.w3schools.com/css/css_icons.asp)

使用icon库进行插入图标的操作

这个网站提供icon的css文件:  
https://www.bootstrapcdn.com/








