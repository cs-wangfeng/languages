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




