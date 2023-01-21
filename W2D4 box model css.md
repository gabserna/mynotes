W2D4
CSS box model
   ┌-------------------------------------------------┐
   |              margin (transparent)               |      
   |   ┌----------------------------------------┐    |
   |   |          border                        |    |   
   |   |   ┌--------------------------------┐   |    |      
   |   |   |      padding                   |   |    |    
   |   |   |  ┌--------------------------┐  |   |    |  
   |   |   |  |   content                |  |   |    |  
   |   |   |  └--------------------------┘  |   |    |  
   |   |   └--------------------------------┘   |    |  
   |   └----------------------------------------┘    |      
   └-------------------------------------------------┘      
               |←---element width-------→|                
   |←-----------------box width---------------------→|      


              1st top ↑
        ┌-----------------┐ 
  4th L←| perimeter order | 2nd R→
        └-----------------┘
            3rd bottom ↓

use as the best way...
margin: to space two elements away from each other
padding: to space out an element from itself

box-sizing: border-box;


to temporaly see boxes y elements:
* {
   outline: 1px solid red !important;
}
----------------------------------------------
<html>
<head>
<style>
div {
  background-color: lightgrey;
  width: 300px;
  border: 15px solid green;
  padding: 50px;
  margin: 20px;
}
</style>
</head>
<body>
<h2>Demonstrating the Box Model</h2>
<p>The CSS box model is essentially a box that wraps around every HTML element. It consists of: borders, padding, margins, and the actual content.</p>
<div>Some text here</div>
</body>
</html>
----------------------------------------------
adding a separated stylesheet:

<head>
<title>Title here</title>
<link rel="stylesheet" href="style.css" />
</head>

element selector:
HTML
<h1 class="intro" id="header">Title here</h1>

h1 {
color: #FF00FF;
margin-bottom: 10px;
}

class selector:
.intro {
color: #aba4ac;
margin-bottom: 10px;
}

id selector:
#header {
color: #aba4ac;
margin-bottom: 10px;
}

compound selector (more than 1)

h1#header {
color: #aba4ac;
margin-bottom: 10px;
}

.h1.header {  /!←BEST/
color: #aba4ac;
margin-bottom: 10px;
}
-------------------------
style priority is determined by position in site:

external <link>
internal <head>
inline style attribute
using! important

priority is also dependent on position in document:

.intro {
color: #444245;
}
.intro {
color: #dddadd;
}
---------------------------
Float left & right
HTML
<article>
<img src="ski.jpg" alt="Ski!" />
<p>Text here</p>
</article>

CSS
img {
float: left;
}
----------------------
Clearing floats
.intro {
clear: both;
}

.group:before,
.group:after {
content: "";
display: table;
}
.group:after {
clear: both;
}
.group {
zoom: 1; /* IE6&7 */
}
------------------------------
Inheritance & specificity
 ┌---------------------------┐ 
 | inline     # of class     |
 | styles     selectors      |
 |  ↓         ↓              |
 |  0,   0,   0,   0         |
 |       ↑         ↑         |
 |    # of ID   # of element |
 |   selectors   selectors   |
 └---------------------------┘
p   0,0,0,1
.   0,0,1,0
#   0,1,0,0
<>  1,0,0,0

.intro p.article { color: #fff; }   0,0,2,1
.intro ul li.artive { color: #98c7d4; }   0,0,2,2
-----------------------------------------
Box model
.classname {
border: 5px solid #fff;        100px content width
padding-left: 10px;             15px padding width
padding-right: 5px;           + 10px border width (5 from each side)
width: 100px;                 =125px box width
}

overflow: visible / auto / hidden / scroll
---------------------------------
Box binding

Positioning
position: static / relative / absolute / fixed

.article {
position: relative;
}
h3 {
position: absolute;
right: 10px;
top: 10px;
}
------------------------------
Z-index
.ski, sled {
z-index: 1;
}
------------------------------
Staying DRY: Don't Repeat Yourself

use parent tags to avoid repeating values
.button {
background: #fff;
border: 1px solid #000;
color: #333;
cursor: pointer;
}
.submit {
background: #555;
}

DRY in HTML (order matters)
<input type="submit" class="button submit" />
<a href="next_page.html" class="button">New</a>

shorthands the order is clockwise top, right, bottom, left
examples:
font: 16px/18px bold italic sans-serif;
border: 3px solid #ccc;
------------------------------
Display types
display: none / block / inline / inline-block
------------------------------
Centering
margin: 0 auto;
text-align: center;
------------------------------
CSS Safety: Protecting your layout

Colapsing margins will not ocurr when one or more block element has: Padding or border, Relative or absolute positioning, a float left or right
-----------------------
Specificity problems
-----------------------
Image issues: Image use

DO NOT
<h1>Random text here</h1>
<img src="divider.jpg" alt="Divider" />

BETTER:
h1 {
background: url(divider.jpg)
margin-bottom: 10px;
padding-bottom: 10px:
}

Content should be marked up as inline images
Layout elements should be defined as background images
------------------------
image cropping

.crop {
height: 300px;
width: 400px;
overflow: hidden;
}
------------------------
Sprightly slaloms: Images replacements
text-indent: -9999px;
------------------------
Sprites

.logo:hover, .logo:focus {
background: url(hover.png);
background-position: 0 -100px;
}                    ↑      ↑
             x-axis change  |
                           y-axis change

base64 encoding:
background-image: url(data:image/png;base64, iVB0......
---------------------------
Pseudo Sitzmark
Pseudo classes
Simplifying with last-child:

li {
border-bottom: 1px solid #aaa;
}
.li:last-child {
border-bottom: 0;
}

Simplifying with nth-child:

li:nth-child(classname) {
background-color: #444245;
}
li:nth-child(odd) {
background-color: #444245;
}

matches items in intervals of a, starting with the element at position b (or 0, if b isn't set)

li:nth-child(an+b) {
li:nth-child(2n) {       /* Even */
li:nth-child(2n+1) {     /* Odd */

:hover / :focus / :active / :visited
:first-child / :last-child / :only-child
:nth-child / :nth-of-type()

p:first-of-type  {
  font-style: italic;
  color: #999
}
.hours li:nth-of-type(odd) {
  background-color: #c5c9cf;
}
.hours li:nth-of-type(4n+1) {
  background-color: #c3e3f3;
}
---------------------------
Pseudo elements
:before / :after

article p:last-child:after {
content: '\2744';
}

:first-letter / :first-line
blockquote:before {
content: '';
}
-----------------------------
.store:hover:before, .store:focus:before {
left: -5px;
top: -5px;
}
.store:hover:after, .store:focus:after {
bottom: -5px;
  right: -5px;  
}
-----------------------------