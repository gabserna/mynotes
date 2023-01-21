Week 6 Day 1 - Interacting with the DOM
	
Iterating Through Nodes
.each(function(index, Element))
is used to iterate through jQuery objects:

$('div').each(function(index)) {
alert(index + '=' + $(this).text());
});

iterates through each div element and returns its index number and text

$('div').each(function(index, elem)) {
alert(index + '=' + $(elem).text());
});

note: elem = this
-----------------------------------------
Iterating Through Nodes Demo

let html = '';
$('div.BlueDiv,div.RedDiv').each(function(index) {
html += "<br />" + index + " " + $(this).text();
});
let output = $('#OutputDiv');
-----------------------------------------
Modifying Properties and Attributes

the this.propertyName statement can be used to modifiy an object's properties directly:

$('div').each(function(i) {
this.title = "MyIndex="+i;
});

iterates through each div and modifies the title. if the propoerty does not exist, it will be added
-----------------------------------------
Accessing Attributes

objects attributes can be accessed using attr():

let val = $('#CustomerDiv').attr('title');

retrieves the value of the title attribute
-----------------------------------------
Modifying Attributes

.attr(attributeName,value) is the method used to access an object's attributes and modify the value:

$('img').attr('title','My Image Title');

changes the title attribute to a value of My Image Title


**Modifying Multiple Attributes

to modify multiple attibutes, pass a JSON object containing name/value pairs:

$('img').attr({   -----------------------
title:'My Image Title',                 |
style:'border:2px solid black;'         |→ JSON objects inside a jQuery object
});  ------------------------------------

JSON objects passed and used to change title and border

JSON delimits objects using { and }
The : (colon) character separates properties and values

{
FirstName: 'John',
LastName: 'Doe',
Address:{
street: '1234 Anywhere st',
City: 'Phoenix',
State: 'AZ',
ZipCode: 85249
  }
}

**Demo
$('div.BlueDiv,Div.RedDiv').each(function(index) {
//raw DOM object
this.title = "Some title;
//using the attr function
$(this).attr('title','Some title 2');

});


$('div.BlueDiv,Div.RedDiv').attr(
  {
  title: 'Some title 3',
  style:'font-size:14pt;background-color:yellow;color:black;'
  }
});

**Chaining
$('div.BlueDiv,Div.RedDiv')
//using the attr function with a map
.attr(
  {
  title: 'Some title 3'
  }
  .css('font-size', '20pt')
  .css('background-color', 'yellow')
  .css('color', 'black');
});
-----------------------------------------
Adding and Removing Nodes

Four key methods handle inserting nodes into elements:

.append()
.appendTo()
.prepend()
.prependTo()

To remove nodes from an element use .remove()

Appending adds children at the end of the matching element:

$('<span>(office)</span>').appendTo('.officePhone');
OR
$('.officePhone').append('<span>(office)</span>');

would result in (office) being added into each .officePhone class element
----
Prepending adds children at the beginning of the matching element:

$('<span>Phone:</span>').prependTo('.phone');
OR
$('.phone').prepend('<span>Phone:</span>');

would result in Phone: being added into each .phone class element

**Wrapping Elements
The following HTML and .wrap() function:
<div class="state">Arizona</div>
$('.state').wrap('<div class="US_State"/>');

Result in:
<div class="US_State">
 <div class="state">Arizona</div>
</div>

**Removing Nodes
.remove() will remove matched elements from the DOM:

$('.phone, .location',).remove();

Will result in objects with .phone or .location classes being removed from the DOM

*Demo
let tdc = $('#tableContainerDiv');
tcd.append('<span style="background-color:green">Appended Child 1</span>');
tcd.prepend('<br /><span style="background-color:green">Prepended Child 1</span>');
$('<br /><span style="background-color:green">Appended Child 2</span>').appendTo(tdc);
$('<span style="background-color:green">Prepended Child 2</span>').prependTo(tdc);

//Wrap
$('span.foo').wrap('div class="RedDiv ParentWrapper" />');
$('div.ParentWrapper').each(function() {
alert ($(this).html());
});

//Remove
$('div.ParentWrapper').remove();

-----------------------------------------
Modifying Styles

the .css() function can be used to modify an object's style:
$("div").css("color", "red");

**Modifying multiple styles
Multiple styles can be modified by passing a JSON object:

$("div").css({
'color': '#ccc'
'font-weight': 'bold'
});
note: can be quoted or non-quoted
-----------------------------------------
Modifying Classes

the four main methods for working with CSS class attributes are:
.addClass()
.hasClass()
.removeClass()
.toggleClass()
----------------
.addClass() adds one or more class names to the class attibute of each matched element:
$('p').addClass('classOne');

more than one class:
$('p').addClass('classOne classTwo');

.hasClass() returns treu if the selected element has a matching class that is specified:
if($('p').hasClass('styleSpecific')){
// perform work
}

.removeClass() can remove one or more classes:
$('p').removeClass('classOne classTwo');

remove all class attributes for the matching selector:
$('p').removeClass();


.toggleClass() alternates adding or removing a class based on the current presence or absence of the class:
$('#PhoneDetails').toggleClass('highlight');

<style type="text/css">
  .highlight{background:yellow;}
</style>

**Demo
$('input[type="text"]').addClass('Highlight');
$('#LastNameTextBox').removeClass('Highlight');

function FocusBlur(tb){
$(tb).toggleClass('Highlight');
}

HTML rev cool function: onfocus and onblur
<input onfocus="FocusBlur(this)" onblur="FocusBlur(this)" ......
-----------------------------------------
JSON = JavaScript Object Notation
map is a JSON object with properties