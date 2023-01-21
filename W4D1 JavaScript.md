W4D1 JavaScript
let: a value that could change!

TIP: AVOID using var, use let or conts instead, for best practice!

variable: 
'text'
49.99 (number)
true (boolean)
can continue with a coma , and always finish with a semicolon ;

valid variable names:
start with one of: _ $ letter
followed by zero or more: _ $ letter number

good variable names:
use descriptive name: account_99
camel name: accountNumber
---------------------------
Common errors declaring variable:

-do not start names with a number
-do not use spaces between the names
-always set a value
---------------------------
Constant: value that does not change!

TIP: When declaring a const always set a value
---------------------------
Types and operators:

numbers: numbers and all the operators asociated with this

strings: using quotes, 'single quotes, "double quotes", `back ticks`.
numbers converted use it like a string

converting tetween types: numberst to text, text to bolean, etc

booleans: true or false

null and undefined

objects and symbols: advanced
---------------------------
typeof is for discover which value is our variable

+, -, *, /, %, =, ++, --
---------------------------
Operator precedence
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence

use MDN (Mozilla Developer Network) to reference

(to see the table of precedence)
---------------------------
Number precision
Negative Numbers
---------------------------
strings
 to show the double quote use: \"world\"";

showMessage(variable);
---------------------------
Converting strings and numbers

numbers to strings: .toString();
strings to numbers: Number.parseFloat("123.12")

NaN = not a number
---------------------------
Boolean

let saved = true;
saved = !saved;        // ! exclamation sign mean NOT and FLIP the result
showMessage(saved);
---------------------------
null and undefined
null: to wipe out a variable value (not showing)
undefined: JS answer to show the value was never assigned in the first place
---------------------------
objects: are created by {}
symbols: (advanced not yet)
---------------------------
console.log()
----------------------------
string interpolation

let messagePerimeter = ("You are going to need " + yardPerimeter + "ft of fence");