Week 5 Day 4 - jQuery Selectors

What are Selectors?

<div id="CustomerDiv" class="Bright">
<span class="Text">WelcomeJohn</span>
</div>

$(selectorExpression) = jQuery(selectorExpression)
---------------------------------
Selecting Nodes by Tag Name
$('p') selects all <p> elements
$('a') selects all <a> elements

$('p,a,span') selects all elements inside

Selecting descendants
$('table tr') selects all tr elements that are descendants of the table element
---------------------------------
Demo
$('div').css('background-color', 'green');

$(document).ready(function () {
$('div').each(function () {
alert($(this).html());
});
});
---------------------------------
Selecting Nodes by ID

$('#myID')
selects <p id="myID"> element
---------------------------------
ID Selector Demo
---------------------------------
Selecting Nodes by Class Name

$('.myClass, .blueDiv, .redDiv')
selects <p class="myClass"> element

$('a.myClass')
selects only <a> tags with class="myClass"
---------------------------------
Class Name Selector Demo

$(document).ready(function () {
$('div.blueDiv, div.redDiv').css('border', '2px solid red');
});
---------------------------------
Selecting Nodes by Attribute Value

$('a[title]')
selects all <a> elements that have a title attibute

$('a[title="ProgrammingInfo"]')
selects all anchor elements that have a "ProgrammingInfo" title attibute value
---------------------------------
Attribute Selector Demo

$(document).ready(function () {
let inputs = $('input[type="text"]');
inputs.css('background-color', 'yellow');
});
---------------------------------
Selecting Input Nodes

$(':input')
selects all inputs elements including: input, select, textarea, button, image, radio, and more.

$(':input[type="radio"]')
targets all radio buttons on the page... but is it the most efficient selector??

we better use:
$('input[type="radio"]')
with out the ":"
---------------------------------
Input Selector Demo

$(document).ready(function () {
let inputs = $(':input');
alert($(inputs[1]).val());    // val = value
});

$(document).ready(function () {
$(':input').each(function () {
let elem = $(this);   //this is wrapped in a jQuery wrapper
alert(elem.val());    // elem = element
  });
});
---------------------------------
Additional Selector Features

**Using contains in selectors
:contains()
will select elements that match the contents within the contains exception:
$('div:contains("pluralsight")')

selects div's that contain the texst pluralsight (note that the match is case-sensitive)
<div>Expert pluralsight Training</div>

**selecting even or odd rows in a table
$('tr:odd') and $('tr:even') is the jQuery syntax for selecting odd or even rows respectively

Remember the index is 0 based - the first row in the table is 0:
odd would return 1,3,5,7,9, etc
even would return 0,2,4,6,8, etc

**selecting the first child
$('element:first-child') selects the first child of every element group:

example:
$('span:first-child') 

<div>
<span>First Child, first group</span>   // <--- will select this
<span>Second Child, first group</span>
</div>
<div>
<span>First Child, Second group</span>   // <--- will select this
<span>Second Child, Second group</span>
</div>

**using starts with in selectors
^ = caret symbol (ascii alt+94)

[attribute^="value")] will select all elements with an attibute that begins with stated value:

$('input[value^="Events"]')
selects any inputs element whose value attibute begins with "Events":

<input type="button" value="Events - World"/>
<input type="button" value="Events - National"/>
<input type="button" value="Events - Local"/>

**using ends with in selectors

[attribute$="value")] will select all elements with an attibute that ends with stated value:

$('input[value$="Events"]')
selects any inputs element whose value attibute ends with "Events":

<input type="button" value="World Events"/>
<input type="button" value="National Events"/>
<input type="button" value="Local Events"/>

**Findin attibutes containing a value

[attribute*="value")] will select all elements with an attibute that contain the stated value:

$('input[value*="Events"]')
selects any inputs element whose value attibute contains with "Events":

<input type="button" value="World Events 2011"/>
<input type="button" value="National Events 2012"/>
<input type="button" value="Local Events 2022"/>
---------------------------------
Additional Selector Features Demo

$(document).ready(function () {
alert($('div:contains("my div")').html());
});


$(document).ready(function () {
$('tr:even).css('background-color', 'yellow');
});
---------------------------------
summary
# for ID seletions
. for class selections
^ for attributes starting with a value
$ for attributes ending with a value
* for attributes containing a value

http://codylindley.com/jqueryselectors/
----------------------------------
put the script tags in the head of the HTML document is NOT a best practice. The better place to put it will be at the end of your body tag. This will ensure that everything on your page has loaded before your script tags load. Here is an example of the best practice:

<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <h1>My page</h1>
    <script src="https://code.jquery.com/jquery-3.5.0.slim.min.js" integrity="sha256-MlusDLJIP1GRgLrOflUQtshyP0TwT/RHXsI1wWGnQhs=" crossorigin="anonymous"></script>
    <script src="app.js"></script>
  </body>
</html>

Notice we put our own script tag that refers to app.js AFTER the jQuery script tag. This is essential! If you were to put your own scripts before the jQuery tag then your code won't be able to use jQuery.
----------------------------------
$(document).ready(function() {
  //writes code here
});

This function simply forces his code to wait for the page to load till his code executes. We will not need to use this function if we put our script tags at the bottom of the body tag.
-----------------------------------
