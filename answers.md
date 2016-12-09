# JavaScript Interview Suggested Answers

## Factual JS Fundamental Questions
> What is a “closure” in JavaScript?

* **Definition:** Closure is when an inner function keeps reference to an outer function’s variables, even after that outer function has finished executing
* **Example:** For example, we could define a function that takes in a number, call it x and returns a function that takes in another number, y and adds x and y. If we call the outer function with 5, the inner function will retain access to the outer function’s argument, and will add 5 to any number it is given
* **Why:** One benefit of closures is they can be utilized to mimic private variables in javascript by defining a variable inside of a function, and returning an object with methods that access or change the value of the variable.
* **References:**  [Javascriptissexy](http://javascriptissexy.com/understand-javascript-closures-with-ease/), [Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

> What is the difference between undefined and not defined in JavaScript?

* **Definition:** Undefined the variable is declared but has no value assigned to it, not defined means the variable is not declared anywhere
* **Example:** If you console.log(a) // reference error a is not defined. If you put var a = 7 on the next line // undefined because of variable hoisting
* **Why:** Note - the type of null is an object, so comparing and undefined variable === null will return false
* **References:** [StackOverflow](http://stackoverflow.com/questions/5101948/javascript-checking-for-null-vs-undefined-and-difference-between-and)

> How do you empty an array in JavaScript?

* **Definition:** you could just set it = [ ], but this will not change other references to the original array, so it will still exist in memory
* **Example:** If you have other references to this array, you need to set its length to 0, create a while loop and pop() while it has a length, or do a splice from 0 to its length, if you want the references to maintain reference to the original array, just set array = [ ]
* **Why:** If you are trying to minimize memory use, make sure you don’t just use =[ ]
* **References:** [StackOverflow](http://stackoverflow.com/questions/1232040/how-do-i-empty-an-array-in-javascript)

> How do you check if an object is an array?

* **Definition:** The type of an array is 'object' in JS, so you need to use `Array.isArray()``
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between classical inheritance and prototypal inheritance?

* **Definition:** In classical inheritance, every time you make an instance of an class, that instance gets a copy of the class’s methods, whereas in prototypal inheritance, failed lookups for an object’s methods fall up the prototype chain, so you don’t have a copy in memory for every method, and you save space in memory
* **Example:** 
* **Why:**
* **References:** []()

> What is function hoisting in JavaScript?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the event loop in JavaScript, and how does it handle synchronous and asynchronous functions?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

## Opinion based

>Why would you use JS?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why did you use AngularJS for your project?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why should we consider using React?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> If you were building Twitter, what tech stack might you use?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why do you want to work at X company?  
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
