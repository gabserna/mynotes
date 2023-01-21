Week 4 Day 2 - If statements and for loops

Conditionals Using if()
Truthy and Falsy
if ... else
Comparing === and ==
The Ternary Operator
Block Scope Using let
Looping with for()
Looping with while()
Looping with do ... while()
*******************************************
shorcuts for visual code studio
! [enter] <!DOCTYPE> ....
li*4>a[enter]
*******************************************
Program flow


Conditionals Using if()

if (5 === 5) {           // true
   console.log('Yes');
}

if (5 > 5) {           // false
   console.log('No');
}

if (5 >= 5) {           // true
   console.log('Yes');
}

IMPORTANT: make sure to use in conditionals three equal sign, in inequality use two equal sign (!==)
----------------------
Truthy and Falsy

falsy: false, 0, "" or '' (empty strings), null, undefined, NaN

truthy: Everything NOT falsy, true, 0.5 and bigger, "0", 

if ( +(1.1 + 1.3).toFixed(2) === 2.4) {
    showMessage('true');
}
----------------------
if () ...else statement


let state = 'FL';
let taxPercent = 0;

if (state === 'FL') {
taxPercent = 7;
}
else if (state === 'NY') {
taxPercent = 8.875;
}
console.log(taxPercent);    //7

-----
let price = 4;
if (price > 10) {
showMessage('true');
}
else if (price < 5) {
showMessage ('less than 5')
}

TIP: is always a good practice to use a curly brackets for a block even if has one line of code
---------------------
Comparing === and ==

TIP: is a good practice to specify with triple equal sign "===" instead of only two "==" to avoid confusion or conversion to strings any number value

equiality: ===
exclamation: !==
---------------------
The Ternary Operator

// (condition) ? true-statement : false-statement
let message = (price > 10)? 'expensive' : 'cheap';
showMessage(message);  // expensive

NOTE: it's called ternary because it have three operator (condition, true-statement and false-statement)
---------------------
Block Scope Using "let" to avoid errors using "var" instead
---------------------
Looping with for()

for (let i = 0; i < 3; i++) {
console.log(i);
}

+++ = increment operator

avoid using an infinite loop to hung the website
---------------------
Looping with while()

let count = 1;
while (count < 5){
console.log(count);
count++;
}

let i = 4;
while (i > 4){
console.log(i);
i--;
}

while operator avoids endless loops
---------------------
Looping with do ... while()

let count = 1;
do {
console.log(count);
count++;
} while (count < 5);

// 1 2 3 4



let count = -4;
do {
console.log(i);
i--;
} while (i < 0);

// -4

---------------------
# Logical Operators
double ampersand(&&)

if(aNumber > 20 && aNumber < 30) {
    aBool = true;
}

double pipe or (||) operator

if(favColor === 'blue' || favColor === 'red') {
   favBlueOrRed = true;
}

## Important Note
javascript looks at each side of the operator individually. JavaScript will first evaluate `favColor === 'blue'` It will then evaluate `'red'`. you must compare the strings on both sides of the or.

if(favColor === 'blue' || favColor === 'red') {
   favBlueOrRed = true;
}






