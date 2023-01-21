Week 5 Day 1 - Javascript Arrays
********************************
Creating and Initializing Arrays

let values = [1, 2, 3 ];

NOTE: items in an array its called elements.

MIXING DATA: you can mix tyoes of data inside of an array, but it's a best practice to always use the same data type within an array, makes things simpler.

const values = ['a', 'b', 'c'];

NOTE: take note of the index showing start counting from 0
----------------------------------
Accessing Array Items
(calling the index)

const values = ['a', 'b', 'c'];
values[0] = 'aaa';
console.log(values [0]); // a
console.log(values [1]); // b
console.log(values [2]); // c
console.log(values [3]); // undefined

value of an index can be easily changed
console.log(values [0]); // aaa
----------------------------------
Manipulating Arrays

//push
const values = ['a', 'b', 'c'];
values.push('d');
console.log(values); // a b c d

//pop
const values = ['a', 'b', 'c'];
const last = values.pop();
console.log(last); // c

//shift
const values = ['a', 'b', 'c'];
const first = values.shift();
console.log(first); // a

//unshift
const values = ['b', 'c'];
values.unshift('a');
console.log(values); // a b c
----------------------------------
slice() and splice()
//slice
const values = ['a', 'b', 'c'];
const newValues = values.slice(1, 2);
console.log(newValues); // b

//splice
const values = ['a', 'b', 'c'];
values.slice(1, 1); // the second value is the number of entries we want to delete, (in this case is 1)
console.log(values); // a c
----------------------------------
Array Searching and Looping

//indexOf
const values = ['a', 'b', 'c'];
console.log(values.indexOf ('c')); // 2
console.log(values.indexOf ('d')); // -1

//filter
const values = ['a', 'b', 'c'];
const set = values.filter(function(item) {
return item > 'b';
});
console.log(set);       // c

//find
const values = ['a', 'bbb', 'c'];
const found = values.find(function(item) {
return item.lenght > 1;
});
console.log(find);     // bbb

//find
const values = ['a', 'b', 'c'];
values.forEach(function(item) {
console.log(item);
});
// a b c

NOTE: when shows -1 means undefined or not found
----------------------------------
Arrays in the DOM

const containers = 
document.getElementByClassName('container');
container[2].classList.add('d-none');
console.log(containers);

it can be used to access containers in a HTML website.
----------------------------------