Week 4 Day 4 - Javascript Objects and the DOM

Objects and the DOM
(Document Object Model)
----------------------------




Object Properties
similar to variables attached to the object

let person {
name: "John",
age: 32,
parTime: false
};
console.log(person.name);     // Johnn
console.log(person.age);     // 32
console.log(person.partTime);     // false
--or also---
person['age'] = 44;
------------------------------------
Object Methods
similar to functions attached to an object

let person {
name: "John",
age: 32,
parTime: false
showInfo: function(){
showMessage('in showInfo');
showMessage(this.name);                    // dont forget to use "this." 
showMessage(this.name + ' is ' this.age); // John is 32
}
};
person.showInfo();

NOTE: it can be called a function but because it's attached to an object, it's traditionally called a METHOD.
------------------------------------
Passing Objects to Functions
IMPORTANT: There is a very big difference between passin an object to a function and passing a built-in type such a string, a number or a boolean value to a function.

let message = 'Hello';
function changeMessage(message) {
message = 'Hi!';
}
changeMessage(message);
showMessage(message);



let person {
name: "John",
age: 32,
parTime: false
};
function incrementAge(person){
person.age++;
}
incrementAge( person );       // passing by reference
showMessage(person.age);

NOTE: we can't change the person object itself as an object, but we can access all of its properties, sub-properties, and methods an this is called "passing by reference"

when we pass objects, we are able to modify their properties and methods, but when we pass some data by value such as a string or a number or a boolean value, any changes made to those will be lost.
------------------------------------
**Standard Built-in Objects

let now = new Date();
showMessage( now.toDateString() );

NOTE: array is a group of objects or a group of values 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference
------------------------------------
The Document Object Model (DOM)

https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model

function showMessage(message) {
document.getElementById('message').textContent = message;
}

function changePercentOff(percentage) {
document.getElementById('percent-off').textContent = pencentage + "% OFF";
}
------------------------------------
Styling DOM Elements

https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style

const variable = document.getElementById('message');
variable.style.fontWeight = '800';

element.style.cssProp='value'         // without dashes as a camel-case
------------------------------------
Detecting Button Clicks

const button = document.getElementById('button-name');

button.addEventListener('click', function() {
console.log('click');
const review = document.getElementById('review');

if (review.classlist.contains ('d-none')){
review.classlist.remove('d-none');
button.textContent = 'CLOSE REVIEW'
}

else {
review.classlist.remove('d-none');
button.textContent = 'SEE REVIEW';
}
});

element.addEventListener(event, fn)
------------------------------------
Showing and Hiding DOM Elements

element.classList.add(className)
element.classList.remove(className)
element.classList.constains(className)
------------------------------------


