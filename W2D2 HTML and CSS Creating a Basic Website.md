HTML and CSS Creating a Basic Website (Interactive)
------------------------------------------------------------
<!DOCTYPE html>
<html>
<head>
</head>
<body>
<h1>PAGE TITLE</h1>
tags: <opening tag> and </closing tag>
<p>paragraph</p>
	<ul>
		<li></li>
		<li></li>
		<li></li>
	</ul>
<ol></ol>
</body>
</html>

anchor = <a></a> ex. <a href="https://google.com">NameLink</a>
target="_blank" to open in a new tab or window
target="_self" to open in the same tab or window
------------------------------------------------------------
CSS

calls selectors without the brackets <>
curly brackets {}
------------------------------
selector {
   property: value;
}

example...
<p>Random text paragraph</p>
p {
  text-decoration: underline;
}
------------------------------

descendent selector
ul li {
   font-size: 24px;
}

TIP: read the selector list from right-to-left, the left-most selector is the parent, with the children following to the right.
---------------------
pseudo-selector
a {
text-decoration: none;
}
(removes the underline from all links on a page)

a:hover {
text-decoration: underline;
color: darkred;
}
(adds an underline and changes the color of all links on a page ONLY when the mouse is over the link)
--------------------
first-child selector
ol li:fist-child {
color:red;
}
--------------------
<style type="text/css">
a {
color:red;
}
</style>
-------------------
Hexagecimal colors in CSS
#FFFF00 / RRGGBB
-------------------
Box model (controls the borders and spacing in between the boxes of each tag)
4 parts of the box:
1- content area (text, images, etc)
2- padding (top, right, left or bottom of the content area)
3- border (top, right, left or bottom of the padding)
4- margin (top, right, left or bottom of the border)

size of the box is content+padding+border+margin
-------------------------------------------------
block level: ul, ol, p, h1, h3
inline level: a, img, input, label
-----------------------------
* option1
* option2
* option3

option1, option2, option3

ul li {
display: inline;
}
-----------------------------
h2 {
padding-top: 6px;
padding-right: 3px;
padding-bottom: 0;
padding-left: 0;
}

or

h2 {
padding: 6px	3px	0	0;
}       (top   right   bottom  left) 
-----------------------------
h2 {
border-width: 6px;
border-style: solid;
border-color: black;
}

or

h2 {
border: 6px	solid	black;
}      (width   style   color)
-----------------------------
html, body, h1, h2, h3, p, ol, ul, li, a {
padding: 0;
border: 0;
margin: 0;
}
--------------
body{
padding: 20px	20px	20px	20px;
}
--------------
h1 {
margin: 10px  0  15px  0;
border-bottom: 1px solid #CCCCCC;
padding-bottom: 3px;
}
--------------
ul {
padding: 0  0  0  50px;
}
--------------
<ul class="nav"></ul>

.nav {
padding-left: 0;
color: #0000af;
text-decoration: none;
}

.nav li {
display: inline;
}
--------------
link CSS file to a HTML page
<head>
<link type="text/css" rel="stylesheet" href="main.css">
<link> this tag doesn't close
**************************************************************
<div class:"header">
<h1>
<ul>
</div>
<div class:"main-content">
<h1>
<ul>
</div>
--------------------
body{
padding: 0 0 0 0;
background-color: #b56663;
}
.header {
padding: 10px 10px 10px 10px;
color: #ffffff
}
.main-content {
padding: 10px 10px 10px 10px;
border: 1px solid #dddddd;
margin: 30px 0 0 0;
}
h1 {
color: #ffffff
}
-------------------------
Centering content
IF: you want to center a ENTIRE block-level tag
AND: it is fixed-witdh
THEN: set the left and right margins to "auto"

margin: 30px auto 0 auto;
text-align: center
------------------------------
3 types of webpages images: Content, Layout and User Interface
<img> not closing
<img src="images/image_name.png" alt="Image description">

<ul class="photos">

.photos {
list-style-type: none;
padding: 0;
}

.photos li {
display: inline;
padding-left: 11px;
}

<div class="header">
<img src="images/logo.png" alt="Logo name"

.header img {
display: block;
margin: 0 auto 0 auto;
}
-------------------------------
body {
background-color: #5f5f5f;
background-image: url(images/filename.jpg);
background-position: top left;
background-repeat: repeat-y; or repeat-x;
}

body {
background: #5f5f5f url(images/filename.jpg) top left repeat;
}
.main-content {
background: #5f5f5f url(images/filename.jpg) top left repeat;
}
.recipes li {
background: #5f5f5f url(images/filename.jpg) top left repeat;
}
---------------------------
HTML
<div class="featured-image">
<h3>featured: filename</h3>
</div>

CSS
.featured-image {
width: 630px;
height: 246px;
background: #5f5f5f url(images/filename.jpg) top left no-repeat;
}

CSS
.featured-image h3 {
margin: 0;
background-color: #333333;
color: #ffffff;
padding: 5px 0 5px 15px;
text-transform: uppercase;
}
---------------------------
Floating images

HTML
<ul class="recipes"
<li>
<img src...>


CSS
.recipes img {
float: left;
padding-right: 10px;
}
---------------------------
FRONT END FOUNDATIONS / FONTS AND FORMS

font-family: Helvetica, Arial, sans-serif;
font-size: 100%;
font: inherit;
font-weight: bold;
font-style: italic;
font-transform: uppercase;

line-height is the spacing between lines

line-height: 16px;
line-height: 26px;

https://mtec.instructure.com/courses/605595/pages/additional-resources-css-fonts?module_item_id=11058895
------------------------------------------
Web forms
Label, textarea, input, submit botton

<form>
<label>Write your name here</label>
<input type="text">
<input type="submit" value="submit">
</form>

<input type="text">
<input type="checkbox">
<input type="radio">
<input type="file">
<input type="password">
<input type="submit">

for/id
<form>
<label for="recipe-name">Recipe name</label>
<input type="text" id="recipe-name">
<input type="submit" value="submit">
</form>

textarea
<label> for="recipe-name">Recipe name</label>
<textarea id="ingredients"></textarea>

CSS
label, input {
display: block;
margin-bottom: 10px;
width: 500px;
}

input [type=submit] {
width: 120px;
font-size: 30px;
}

input [type=text] {
border:2px solid #7facaa;
font-size: 24px;
padding: 7px;
}

textarea{
width: 445px;
heigth: 400px;
padding: 7px;
border:2px solid #7facaa;
margin-bottom: 25px;
font-size: 20px;
}

checkbox
<form>
<label for="newsletter">Get Newsletter</label>
<input type="checkbox" id="newsletter">
</form>

CSS
input[type=checkbox], label[for=newsletter] {
display: inline;
}