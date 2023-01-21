// Go back to the previous assignment for the syntax of a basic for loop if you need it.

// This time we want to iterate through 0 to 19 (20 times) instead of 0 to 9.
// Same as the last assignment we have our addTo variable where
// the iterator will be added to each loop.

let addTo;
function adding(num) {
  addTo = num;
  //Code here
  for (let num = 0; num < 20; num++){
    addTo += num;
  }
}
adding();

//Create a for loop that iterates through 20 to 29.
//Add the iterator to the anotherAdd variable each loop.

let anotherAdd;
function adding1(num) {
  anotherAdd = num;
  //Code here
    for (let num = 20; num < 29; num++){
    anotherAdd += num;
  }
}
adding1();

// Now we want a loop that adds to our variable moreAdding.
// This time we want it to add every 5th number starting at 0
// all the way to 100. ex. 0,5,10,15,20,25,etc.
// variable + 0
// variable + 5
// variable + 10
// all the way to 100
// Unsure how to do this? Keep in mind our iterator(i) has always
// gone up by one each loop so far. How could we make the iterator(i)
// go up by 5 each loop?
// You could also consider using the modulus operator:
// https://riptutorial.com/javascript/example/760/remainder---modulus----

let moreAdding;
function adding2(num) {
  moreAdding = num;
  //Code here
  for (let num = 0; num <= 100; num++){
    if (num % 5 === 0) {
            moreAdding += num;
        }
    }
}
adding();