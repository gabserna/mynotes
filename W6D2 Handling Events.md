Handling Events

jQuery Event Model Benefits


Using JavaScript to Handle Events Demo

to check if the browser is supported

var button = document.getElementById('SubmitButton');
  if (document.addEventListener){
    button.addEventListener('click',function(){alert('ClickedButton');},false);
}
else {
button.attachEvent('onclick', function () ( alert ('Clicked IE Button*); });
}
--------------------------------------
Handling Events

jQuery event shortcuts:
click()
blur()
focus()
dblclick()
mousedown()
mouseup(
mouseover()
keydown()
keypress()

See more at http://api.jquery.com/category/events



dblclick() example:

let divdbl = $( "div" ).first();
divdbl.dblclick(function() {
  divdbl.toggleClass( "dbl" );
});
(https://api.jquery.com/dblclick/)
--------
Handling click events

.click(handler(eventObject)) is used to listen for a click event or trigger a click event on an element
example 1
$('#myID').click(function(){
alert('The element myID was clicked');
});

example 2
Raising a click event from within another function:

$('#otherID').click(function(){
$('#myID').click();
});

this would fire when the element otherID was clicked and raise the click event for myID
--------------------------------------
Click Event Demo

$(document).ready(function () {
    WireEvents();
});
function WireEvents () {
$('#SubmitButton').click(function(){
let firstNameVal = $(#FirstNameTextBox ) .val();
let lastNameVal = $(#LastNameTextBox ) .val();
§('#DivOutput').text(firstNameVal + ' ' + lastNameVal);
});
--------------------------------------
Change Event Demo

//Handle select
$('#StatesSelect').change(function(){
alert($(this).val());
});

$('.My Input').change (function () {
alert($(this).val());
$(this).addClass('Highlight');
});
--------------------------------------
Mouse Events Demo

$('#MyDiv, tr').mouseenter(function(){
  Toggle(this);
$(this).css('cursor','pointer');
})
.mouseleave (function () {
  Toggle($(this));
})
.mouseup (function (e) {
alert($(e.target).attr('id'));
$(this). text('X: ' + e.pageX + 'Y: ' + e.pageY);
});
function Toggle(div) {
$(div).toggleClass('Highlight');
}
--------------------------------------
Binding to Events

.on(eventType, handler(eventObject)) attaches a handler to an event for the selected element(s)

$('#myID').on('click', function(){
   //handle click event
});

Using off()
.off(event) is used to remove a handler previously bound to an element:

$(#test").click(handler); //can be unbound using
$("#test").off();

- Specific events can also be targeted using off():
$ ('#test').off("click*);


Binding Multiple Events with on()

-on() allows multiple events to be bound to one or more elements
-Event names to bind are separated with a space:

**Demo
$('#MyDiv').on('mouseenter mouseleave',
function(){
$(this).toggleClass('Highlight');
$(this).css('cursor', 'pointer');
if (e.type == 'mouseup') {
$(this). text('X: ' + e.pageX + 'Y: ' + e.pageY);
}
});
--------------------------------------
live(), delegate() and on() Functions
- live(), delegate(), and on() allow new DOM elements to automatically be "attached" to an event handler
- Allow children to be added to a container without explicitly attaching an event handler to each child
- Event handlers can be set using live()
- The document object handles events by default
- Works even when new objects are added into the DOM:

$ ('.someClass').live('click', someFunction);

NOTE: live() removed in jQuery 1.9
- Stop live event handling using die():

$(".someClass').die('click', someFunction);


Using delegate()
- Newer version of live() added in jQuery 1.4
- A context object (#Divs in the sample below) handles events by default rather than the document object
- Works even when new objects are added into the DOM:

$('#Divs').delegate('div','click',someFunction);

- Stop delegate event handling using undelegate()

IMPORTANT!!!!: The on() function
is a new replacement for the following:

bind()
delegate()
live()

$ ('div').on('click',function(){
alert('Clicked button! ') ;
});


Using on() with Child Objects
- The on() function can be used in place of live() and delegate()
- Works when new objects are added into the DOM:

$ ("#MyTable tbody"). on("click", "tr"
function(event){
alert('Row was clicked and bubbled up');
*);


Using on() with a Map
- Multiple events and handlers can be defined in on() using a "map":

$("#MyTable tr").on({
  mouseenter:function(){
  $(this).addclass("over");
},
mouseleave:function(){
  $(this).removelass("out");
}
}):

**Using on() Demo

$ ('tr').on('click',function(){
alert($(this).html()) ;
});

$ ('#customers tbody').on('click', 'td', function(){
alert($(this).html()) ;
});


$(document).ready (function () {
var tbody = $(*#customers tbody');
});
tbody.append("<tr>‹td>Jane</td›<td>Doe</td›</tr›');
tbody.on('click')'td', function () (
alert($(this).text());
  });
});
--------------------------------------
Handling Hover Events
- Hover events can be handled using hover():
$(selector).hover(handlerIn, handlerOut)
- handlerIn is equivalent to mouseenter and handlerOut is equivalent to mouseleave

Using hover
This example highlights #target on mouseenter and sets it back to white on mouseleave

$('#target').hover(
  function(){
  $(this).css('background-color', '#00FF99');
},
function(){
$(this).css('background-color','#FFFFFF');
}
);


Alternate Hover Example  (shortcut)
- Another option is $(selector).hover(handlerlnOut)
- Fires the same handler for mouseenter and mouseleave events
- Used with jQuery's toggle methods:

$ ('p').hover(function() {
  $(this).toggleClass('over');
});
This code will toggle the class applied to a paragraph element

**Hover Events Demo

$('#target').hover(
  function(){
    // equivalente to mouseenter
  $(this).css('background-color', '#00FF99');
},
function(){
    // equivalente to mouseleave
$(this).css('background-color','#FFFFFF');
}
);

//easier
$ ('p').hover(function() {
  $(this).toggleClass('className');
});

//bonus
$('#MyTable tr'). toggle(
  function () {
$(this).css('background-color', '#efefef'):
};
  function () {
$(this).css("background-color", "#fff"):
};
  function() {
$(this).css('background-color', 'Yellow');
}
);
---------------------------------
Summary

- jQuery simplifies handling cross-browser event attachments
- Many built-in shortcut functions such as click() can be used
- bind() and unbind() provide a flexible way to work with different events
- live() and delegate() both allow future child elements to be wired to event handlers
- The hover() function provides a simple way to handle mouseenter and mouseleave events
- Combine hover() with toggleClass() to easily swap out CSS classes on an element