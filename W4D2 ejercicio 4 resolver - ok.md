Demonstrate a for loop
We have a variable addTo. The user will be able to enter any Number to that variable. Create a for loop that loops 
10 times(0-9). Every time the loop runs add the iterator to the addTo variable and assign the value to the addTo variable

Note: The iterator is the variable you declare in parenthesis of the for loop. This variable is usually called 'i'.


let addTo;
function adding(myNum) {
    addTo = myNum;
  
  //write for loop here
  for (let myNum = 0; myNum < 10; myNum++){
    addTo += myNum;
  }
}
adding();