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










