// Look at the instructions.md file first!!

// Problem 1
// Lets start simple. We will do something very similar to how a 
// for loop works and what the instructor did in the videos when 
// demonstrating while loops.

// We have a variable 'i' that is set to 0. Create a while loop that loops
// five times. Increment 'i' each time.

let i = 0;

//write loop here
 while (i < 5){
  console.log(i);
  i++;
 }
// Problem 2
// Another way to write a while loop is to have a boolean variable 
// where the condition goes and then test every time if you need to
// change the boolean to false.

// Below we have a variable lessThan5 and it is set to true.
// Create a loop that tests if our variable 'j' is less than 5.
// If it is less than 5 then Increment it by 1. If it is not 
// less than 5 then set our lessThan5 variable to be false.

let lessThan5 = true;
let j = 0;

while(lessThan5 < 5) {
  j++;
  lessThan5 = false;
  lessThan5 += j;
}



// Example of what the number game would look like:
// Couple things to note:
// Math is a built in object in javascript.
// Math.round() will round a decimal number to a whole number.
// Math.random() returns a decimal number between 0 to 1.
// (But not including 1)

function guessNumberGame(guess) {
  let guessing = true;
  let number = Math.round(Math.random() * 100);
  while(guessing) {
    if(guess === number) {
      guessing = false;
    } else {
      guess = Number(prompt("That number didn't work. Try again: "));
    }
  }
}

// Problem 3
// We will give you a number through the 'num' parameter
// Create a while loop that will loop 'num' amount of times.
// For example if num is 3 then your while loop should loop 3 times
// If num is 20 then the loop should loop 20 times.
// Increment k every loop.

let k = 0;
function keepLooping(num) {
  while (num > k){
    k++;
  }
  return k;
}
keepLooping();