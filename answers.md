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
* **Example:** Use Array.isArray(), or Object.prototype.toString.call( someVar ) === '[object Array]' for older browsers
* **Why:** Arrays type is object, so to differentiate you need to use Array.isArray
* **References:** [StackOverflow](http://stackoverflow.com/questions/22289727/difference-between-using-array-isarray-and-instanceof-array)

> What is the difference between classical inheritance and prototypal inheritance?

* **Definition:** JavaScript uses protoypal inheritance, either through the portotypal or constructor pattern. Languages like C++, Java, C# and Python support Classical Inheritance. In Classical inheritance is classes are immutable, objects can only be created by instatiating classes, and classes inherit from other classes. Prototypal inheritance is dynamic, meaning you can add methods to the prototypes on the fly, and objects inherit from other objects through the protoype chain.
* **Example:** JavaScript uses prototypal inheritance with the constructor pattern (using `new` keyword) and the prototypal pattern (`Object.create()`). Traditional languages use classical inheritance
* **Why:**
* **References:** [Why Prototypal Inheritance Matters](http://aaditmshah.github.io/why-prototypal-inheritance-matters/)


> What is the event loop in JavaScript, and how does it handle synchronous and asynchronous functions?

* **Definition:** The event loop can be conceptualized as a stack to handle function calls, a 'hold box' to handle asynchronous functions, and a queue, to hold async functions that have completed their assignment. The JS engine first clears the function call stack. As it does, if there is an async function, it will go into the 'hold box' until it completes, at which point it moves to the queue. Then if there is anything in the queue that has finished its async task, it will be moved into the stack and execute. Events from the queue only move onto the stack when the stack is clear.
* **Example:** If you use a setTimeout of 0 on a function nested inside another function, it will not complete until the containing function has finished executing.

```javascript
function outer() {
  console.log('first')
  setTimeout(() => console.log('second'), 0)
  last()
}
console.log('done')

function last() {
  console.log('third')
}
// Will log 'first', 'third', 'done', 'second'
```
* **Why:** Javascript is single threaded, and it is important to understand what happens with async functions, and also realize that if you have a lot of async functions firing repeatedly, you will fill up the queue, which, when it executes, can block the stack and slow down your program. Also setTimeouts do not guarantee an exact time until the function executes, just the minimum wait before it will execute.
* **References:** [Mozilla](https://developer.mozilla.org/en/docs/Web/JavaScript/EventLoop)

> Explain event delegation

* **Definition:** Event delegation allows you to add listeners for events to parents in the DOM, instead of having to add them to each child node. Events bubble up, and you can access which child was actually clicked through the target property of the event.
* **Example:**
```javascript
// Get the element, add a click listener...
document.getElementById("parent-list").addEventListener("click", function(e) {
  if(e.target && e.target.nodeName == "LI") {
    // List item found!  Output the ID!
    console.log("List item ", e.target.id.replace("post-", ""), " was clicked!");
  }
});
```
* **Why:** This allows you to add less click or event handlers, and is much simplier to use with dynamically generated lists that require listeners. It is also useful for implementing highlighting in a list or table. You can put a listener on the parent, and highlight whichever child was clicked.
* **References:** [SitePoint](https://www.sitepoint.com/javascript-event-delegation-is-easier-than-you-think/), [David Walsh Blog](https://davidwalsh.name/event-delegate)

> Explain how this works in JavaScript

* **Definition:** `this` typically refers to the context that a function is called in. Usually you can use the left of the dot rule to determine how `this` is bound.
* **Example:** An example of the left of the dot rule:
```javascript
var person = {
  quote: 'Bazzinga',
  talk: function() {
    console.log(this.quote)
  }
}
person.talk();
// Logs 'Bazzinga'
```
* Typically the object on which a method is called is the context. You can override this behavior using bind, call, or apply. They allow you to specify a different context by passing it as the first argument to bind / call / apply. In the global context, `this` refers to the Window object (unless you are in "use strict mode" - in that case it will be undefined). When passing a method that uses `this` internally as a callback function, the method can loose it's `this` binding at call-time (eg. inside a setTimeout). In these cases, you need to either bind the `this` value when you pass it as a callback, or wrap it in an arrow function, since these set `this` bindings lexically, rather than at call-time.
* **Why:** It's important to be aware of maintaining the correct binding for `this` when passing methods to higher order functions, such as setTimeout, map, or reduce.
* **References:** [Mozilla](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/this), [JS is Sexy](http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)

> Explain how prototypal inheritance works
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What do you think of AMD vs CommonJS?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain why the following doesn't work as an IIFE: function foo(){ }();. What needs to be changed to properly make it an IIFE?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's a typical use case for anonymous functions?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How do you organize your code? (module pattern classical inheritance?)
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between host objects and native objects?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Difference between: function Person(){} var person = Person() and var person = new Person()?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between .call and .apply?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain Function.prototype.bind.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> When would you use document.write()?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between feature detection feature inference and using the UA string?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain Ajax in as much detail as possible.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the advantages and disadvantages of using Ajax?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain how JSONP works (and how it's not really Ajax).
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Have you ever used JavaScript templating?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain "hoisting".

* **Definition:** 'Hoisting' is when function declarations and variable declarations are always moved invisibly to the top of their containing scope by the JavaScript interpreter. For variable declarations (and function expressions - `var func = function() {}`), note that the assignment portion is not hoisted, only the name.
* **Example:**
```javascript
foo(); //foo is not defined
bar();
var foo = function() {
  alert("This function won't be hoisted.");
}
function bar() {
  alert("This function is!");
}
```
* **Why:** Hoisting is actually the result of the JavaScript interpreter implementation. Code interpretation is done in two passes. First pass processes variable and function declarations. Second pass is where code execution happens. You can use it to forward reference a function, though - as in use a function before it's declared.
* **References:** [Adequately Good](http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html), [StackOverflow](http://stackoverflow.com/questions/15005098/why-does-javascript-hoist-variables)

> Describe event bubbling.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the extent of your experience with Promises and/or their polyfills?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the pros and cons of using Promises instead of callbacks?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What tools and techniques do you use debugging JavaScript code?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What language constructions do you use for iterating over object properties and array items?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the difference between mutable and immutable objects.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is an example of an immutable object in JavaScript?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the pros and cons of immutability?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the difference between synchronous and asynchronous functions.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is event loop? What is the difference between call stack and task queue?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the differences on the usage of foo between function foo() {} and var foo = function() {}

* **Definition:** So this is the difference between function declarations and function expressions. Function declarations define a named function variable without requiring variable assignment and are standalone constructs. Function expressions, on the other hand, don't start out with `function` and can be named or anonymous. On the difference of usage, function declarations have the benefit of being hoisted.
* **Example:**
```javascript
//function declaration
function bar() {
    return 3;
}
//anonymous function expression
var a = function() {
    return 3;
}
//self invoking function expression
(function sayHello() {
    alert("hello!");
})();
```
* **Why:** Normally function declarations and function expressions can be used interchangeably, but there are times when function expressions result in easier to understand code without the need for a temporary function name. Function expressions can also be used as closures, as arguments to other functions, and as IIFEs (Immediately Invoked Function Expressions).
* **References:** [JavaScript, JavaScript...](https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/), [SitePoint](https://www.sitepoint.com/function-expressions-vs-declarations/)

> Why is extending built-in JavaScript objects not a good idea?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between == and ===?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the same-origin policy with regards to JavaScript.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why is it called a Ternary expression what does the word "Ternary" indicate?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is "use strict";? what are the advantages and disadvantages to using it?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> * Is JavaScript statically or dynamically typed? Is JavaScript strongly typed or loosely typed? What do those terms mean?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> * Practically speaking, what's a "declarative" language?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> * Is JavaScript a functional language? What does it mean for a language to be "functional"?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> * What's an IIFE in JS? When would you use it?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is JSONP
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

## Data Structures Questions
> * What is the average and worst-case time complexity of access, search, and insertion for common data structures? For each answer, briefly explain why.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> * What's a "tuple"? What's a "triple"? What's the difference between a tuple and a set?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()


## Front End Questions
* If you have 5 different stylesheets how would you best integrate them into the site?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [ryowheatley](http://ryowheatley.blogspot.com/2016/12/master-vs-multiple-stylesheets-short.html)  [impressiveWebs](https://www.impressivewebs.com/best-way-add-css-web-page/
  http://ryowheatley.blogspot.com/2016/12/master-vs-multiple-stylesheets-short.html)


> Can you describe the difference between progressive enhancement and graceful degradation?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [SitePoint](https://www.sitepoint.com/progressive-enhancement-graceful-degradation-basics/),
  [W3](https://www.w3.org/wiki/Graceful_degradation_versus_progressive_enhancement)


> Name 3 ways to decrease page load (perceived or actual load time).
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> If you jumped on a project and they used tabs and you used spaces what would you do?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the importance of standards and standards bodies.
* **Definition:**
* **Example:**
* **Why:**
* **References:** [SitePoint](https://www.sitepoint.com/importance-web-standards/),
  [Wikipedia](https://en.wikipedia.org/wiki/Web_standards)
  [Wikipedia2](https://en.wikipedia.org/wiki/Standards_organization)
]

> What is Flash of Unstyled Content? How do you avoid FOUC?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [TechRepublic](http://www.techrepublic.com/blog/web-designer/how-to-prevent-flash-of-unstyled-content-on-your-websites/)  
  [RobertMullaney](http://www.robertmullaney.com/2011/08/29/prevent-flash-of-unstyled-content-fouc-jquery/)


> Explain some of the pros and cons for CSS animations versus JavaScript animations.
* **Definition:**
* **Example:**
* **Why:**
* **References:** [Css Tricks](https://css-tricks.com/myth-busting-css-animations-vs-javascript/)  


> What does CORS stand for and what issue does it address?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS)  


> What does a doctype do?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [HTML Goodies](http://www.htmlgoodies.com/html5/markup/the-doctype-tag-and-its-effect-on-page-rendering.html#fbid=5hnZLqwgxDp)  
  [Mozilla](https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode)
  [SitePoint](http://reference.sitepoint.com/css/doctypesniffing)
  [StackOverflow](http://stackoverflow.com/questions/7695044/what-does-doctype-html-do#answer-7695336)


> What's the difference between full standards mode almost standards mode and quirks mode?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [Mozilla](https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode)  
  [Mozilla2](https://developer.mozilla.org/en-US/docs/Gecko's_Almost_Standards_Mode)
  [SitePoint](http://reference.sitepoint.com/css/doctypesniffing)


> What's the difference between HTML and XHTML?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [SitePoint](https://www.sitepoint.com/web-foundations/differences-html-xhtml/)  


> Are there any problems with serving pages as application/xhtml+xml?
* **Definition:**
* **Example:**
* **Why:**
* **References:** [456 BereaStreet](http://www.456bereastreet.com/archive/200501/the_perils_of_using_xhtml_properly/)  
  [SitePoint](https://www.sitepoint.com/web-foundations/differences-html-xhtml/)
  [StackOverflow](http://stackoverflow.com/questions/351380/what-are-the-problems-associated-with-serving-pages-with-content-application-xh#answer-351908)

> How do you serve a page with content in multiple languages
* **Definition:**
* **Example:**
* **Why:**
* **References:** [No Mensa](https://www.nomensa.com/blog/2010/7-tips-for-multi-lingual-website-accessibility)  
  [Pro TekConsulting](http://www.pro-tekconsulting.com/blog/how-do-you-serve-a-page-with-content-in-multiple-languages/)

> What are data- attributes good for?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe the difference between a cookie sessionStorage and localStorage.
* **Definition:**
* **Example:**
* **Why:**
* **References:** [C SharpCorner](http://www.c-sharpcorner.com/uploadfile/cd7c2e/difference-between-local-storage-session-storage-ans-cookie/)  


> Describe the difference between `<script>` `<script async>` and `<script defer>`. How can you leverage these to reduce page load times?

* **Definition:**
  * Script - embed executable JavaScript, fetched & executed immediately - next line is not parsed until this one completes
  * Script Async - Continue parsing while this loads, only works with src, executes at first opportunity after it’s available, before page loads - order of async execution may change from order on page
  * Script defer - execute after the document is parsed, but before it loads. Defer tags will execute in order
* **Example:**
  * If the script is modular and does not rely on any scripts then use async.
  * If the script relies upon or is relied upon by another script then use defer.
  * If the script is small and is relied upon by an async script then use an inline script with no attributes placed above the async scripts.
* **Why:** Async helps the page load faster (by not pausing HTML parsing to download), defer does the same, but guarantees order of execution
* **References:** [Growing with the web](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)



> Why is it generally a good idea to position CSS `<link>`s between `<head>``</head>` and JS `<script>`s just before `</body>` or use `async` or `defer`? Do you know any exceptions?

* **Definition:** Things needed to render the page should be loaded in the head, resources that manipulate the page can be loaded at the end of the body, or can be asynchronously loaded while the HTML parser continues on
* **Example:** CSS and external libraries should be loaded in the head, while your JS files can be loaded after the HTML body. One exception is that if your JS code depends on a library (like JQuery), you need to make sure the library loads before your scripts. To do this place the library in the head and the script at the end of the body, or (even better solution) put an `async` tag on the script that needs JQuery.
* **Why:** You can reduce load times by positioning loading resources that are not necessary to render the HTML after rendering. The HTML parser is blocking, and will wait for external resources to be loaded before it continues.
* **References:** [Stack Overflow](http://stackoverflow.com/questions/436411/where-is-the-best-place-to-put-script-tags-in-html-markup)

> What is progressive rendering?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Have you used different HTML templating languages before?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between classes and IDs in CSS?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between "resetting" and "normalizing" CSS? Which would you choose and why?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe Floats and how they work.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe z-index and how stacking context is formed.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe BFC(Block Formatting Context) and how it works.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the various clearing techniques and which is appropriate for what context?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain CSS sprites and how you would implement them on a page or site.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are your favourite image replacement techniques and which do you use when?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How would you approach fixing browser-specific styling issues?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How do you serve your pages for feature-constrained browsers?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the different ways to visually hide content (and make it available only for screen readers)?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Have you ever used a grid system and if so what do you prefer?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Have you used or implemented media queries or mobile specific layouts/CSS?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Are you familiar with styling SVG?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How do you optimize your webpages for print?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are some of the "gotchas" for writing efficient CSS?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the advantages/disadvantages of using CSS preprocessors?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How would you implement a web design comp that uses non-standard fonts?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain how a browser determines what elements match a CSS selector.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe pseudo-elements and discuss what they are used for.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

* **Definition:** The standard box model is margin-border-padding-content, where the width and height of a box only include the content. The padding, border, and margin are added on outside of the width. You can use the box-sizing property in CSS to render a different box model.
* **Example:** [Example image](http://www.planetoftunes.com/website-design/css/media/boxmodel.gif)
* **Why:**
* **References:** [w3 schools](http://www.w3schools.com/css/css_boxmodel.asp), [Quora](https://www.quora.com/What-is-your-understanding-of-the-box-model-How-would-you-tell-the-browser-in-CSS-to-render-your-layout-in-different-box-models)


> What does { box-sizing: border-box; } do? What are its advantages?

* **Definition:** The width and height properties include content, border and padding, but not margin
* **Example:** [w3 Schools](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_box-sizing2)
* **Why:** This allows you to add padding and borders without changing the total width and height of the element
* **References:** [w3 Schools](http://www.w3schools.com/cssref/css3_pr_box-sizing.asp)

> List as many values for the display property that you can remember.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between inline and inline-block?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between a relative fixed absolute and statically positioned element?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> The 'C' in CSS stands for Cascading. How is priority determined in assigning styles (a few examples)? How can you use this system to your advantage?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What existing CSS frameworks have you used locally or in production? How would you change/improve them?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Have you played around with the new CSS Flexbox or Grid specs?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How is responsive design different from adaptive design?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Have you ever worked with retina graphics? If so when and what techniques did you use?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Is there any reason you'd want to use translate() instead of absolute positioning or vice-versa? And why?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's the difference between an "attribute" and a "property" in HTML?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Difference between document load event and document DOMContentLoaded event?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why is it in general a good idea to leave the global scope of a website as-is and never touch it?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives and why would you use those?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain what a single page app is and how to make one SEO-friendly.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are some ways you may improve your website's scrolling performance?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> In the MVC design pattern what's M stands for?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the difference between layout painting and compositing.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Traditionally why has it been better to serve site assets from multiple domains?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between display: none and visibility: hidden?

* **Definition:** Display: none means the tag does not appear on the page, and there is no space allocated for it between other tags. Visibility: hidden means the tag is not visible, but the space it would occupy is still reserved on the page.
* **Example:**
* **Why:** You can still interact with the elements through the DOM.
* **References:** [Stack Overflow](http://stackoverflow.com/questions/133051/what-is-the-difference-between-visibilityhidden-and-displaynone)

> What are some ways to make a page SEO friendly
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between document load and document ready?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe the MVC pattern
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the differences between React and Angular.

* **Definition:** React interacts with a virtual DOM, which it diffs by comparing it against the real DOM and re-renders only changed components, while Angular is tightly coupled with the DOM - it watches for changes in data through dirty checking, and directly updates the DOM accordingly. Angular injects data with two way data binding via scopes. React has one way databinding through props, and relies on state to propogate changes through the components in the app. Angular is a full framework, while React is a library for managing view through composable components. React uses JSX, so your HTML and JS live in the same file.
* **References:** [terropa](http://teropa.info/blog/2015/03/02/change-and-its-detection-in-javascript-frameworks.html), [Quora](https://www.quora.com/What-are-the-differences-between-Angular-js-and-React-js)



## Testing Questions


> What are some advantages/disadvantages to testing your code?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What tools would you use to test your code's functionality?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between a unit test and a functional/integration test?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the purpose of a code style linting tool?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What tools would you use to find a performance bug in your code?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Present a quick overview of TDD.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()


## Web Knowledge Questions

> Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.

* **Definition:** 
  Super simplified version: 
  1. Browser checks the cache, if it finds the requested object and it's fresh, skip to #9
  2. Broswer asks OS for server's IP address
  3. OS makes a DNS lookup and gives the IP address to the browser
  4. Browsesr opens a TCP connection to the server (more complex for HTTPS)
  5. Browser sends the HTTP request through the TCP connection
  6. Browser recieves the HTTP response, and either closes the connection or reuses it for another request
  7. Browser checks status code (3xx, 4xx, 5xx or 2xx)
  8. If possible, browser caches response
  9. Browser decodes response
  10. Browser determines what to do with the response (Is it HTML, image, audio?)
  11. Browser renders response
* **References:** [Stack Overflow](http://stackoverflow.com/questions/2092527/what-happens-when-you-type-in-a-url-in-browser)

> What is SSL? What is TLS?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What security issues go along with having an input form? How would you handle those? Can you think of anyother parts of your site that are security issues?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What is the difference between a socket and a port?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What is the "same-origin policy"?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What is the difference between encryption and hashing?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What are rainbow tables? How are they used?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What are salts? Why are they useful?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
> What is the difference between encoding, obfuscation, minification, and comression?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()


## Back End Questions

> What are the differences between Long-Polling Websockets and Server-Sent Events?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are HTTP methods? List all HTTP methods that you know and explain them.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 200.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 201.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 204.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 301.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 400.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 404.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 409.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe server response code 500.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are some advantages of CDNs? Disadvantages?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is a reverse proxy?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Why Functional Programming matters? When should a functional programming language be used?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Pro and cons of mutable and immutable values.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the tradeoffs of client-side rendering vs. server-side rendering?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How would you manage the migration of a project from MySQL to PostgreSQL?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> How is Lazy Loading achieved? When is it useful? What are its pitfalls?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> In which case would you use a document database like MongoDB instead of a relational database like MySQL or PostgreSQL?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's a rebase?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the biggest difference between Agile and Waterfall?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> When is a cache not useful or even dangerous?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is the difference between emergent design and evolutionary architecture?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Scale out vs scale up: how are they different? When to apply one when the other?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What's Two Factor Authentication? How would you implement it in an existing web application?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the basic structure of a MIME multipart message when used to transfer different content type parts. Provide a simple example.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Explain the difference between stateless and stateful protocols. Which type of protocol is HTTP? Explain your answer.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe the key advantages of HTTP/2 as compared with HTTP 1.1.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is a “MIME type” what does it consist of and what is it used for? Provide an example.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What are the main differences between a document database and a SQL database? Which would you consider "more efficient"?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe the benefits of Redis.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Describe the benefits of Elasticsearch
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()


> How do you allow CORS requests?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

## General CS Questions

> What is a design pattern? Can you describe one?

* **Definition:** A design pattern defines a standard approach to handle a common problem in computer science
* **Example:** There are three basic categories of design patterns: Behavioral, structural and creation patterns
  1. **Creational Design Patterns:** Provide instatiation mechanisms for object creation
    * *Factory:* It rolls the creation of multiple classes into a single function, like a factory that can make multiple products. By providing the right context to the factory method, it will return the desired object. The class of the returned object comes from the actual subclass that created it, not from the factory itself.
    * *Builder:* Creates complex objects by using simple objects, and building the final object step by step. This allows for parsing a complex object to create different representations (ie. converting RTF files to ASCII, TeX, or text widget all with one builder or building a fast food meal from an order). It is useful when there is a common input, and many possible output representations.
    * *Abstract Factory:* Interface for creating families of related or dependent objects without specifying concrete classes. Heirarchy is based on a matrix of products and platforms. (ie. A factory that can create an application to work on a specific platform)
    * *Prototype:* Base class maintains a dictionary of all prototype information. Clones of the prototype are made to create objects. While the factory method does creation through inheritance, the prototype method does creation through delegation. Cloning is cheap, so this method is useful when there is little variation in initialization parameters, allowing you to avoid expensive creation from scratch like in the factory method.
    * *Singleton:* For creating one and only one instance of an object. It uses lazy initialization (creation on first use). State objects are often Singletons.
  2. **Structural Design Patterns:** Deal with relationships between entities, making it easier for those entities to work together
    * *Decorator:* Adds new or additional behavior to an individual object during run-time (post-compiling), as needed. The decorator pattern offers more flexibility over inheriting from a prototype when you have objects that have base methods and properties in common, but then each have some subset of a larger set of additional methods and properties. Rather than building subclasses for each one of those possible combinations, you can use decorators to add the needed methods or functionality.
    * *Adapter:*
    * *Bridge:*
    * *Facade:*
    * *Composite:*
    * *Proxy:*
    * *Private Class Data:*
    * *Flyweight:*
  3. **Behavioral Design Patterns:** Used in communications between entities, and make that communication easier and more flexible
    * *Asynchronous:*
    * *Observer:*
    * *State:* An Object's behavior changes when its internal state changes. ex. DVD remote control - when in moviePlayingState, pressing the play button pauses the movie, when in moviePausedState, pressing the play button plays the movie
    * *Strategy:*
    * *Chain of Responsibility:* A series of receivers or objects attempt to handle and resolve a request, or else they pass it to the next object in the chain. ex. Middleware in Express is a variant, or Promises using .catch() where if one attempt fails, a new object picks it up
    * *Command:*
    * *Iterator:*
    * *Interpreter:*
    * *Mediator:*
* **Why:** These are well-thought out solutions to common programming problems, and provide a solid foundation for developing programming languages and general problem solving
* **References:** [tutsplus](https://code.tutsplus.com/articles/a-beginners-guide-to-design-patterns--net-12752), [Source Making](https://sourcemaking.com/design_patterns)

> What is a programming paradigm? Can you describe one?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

## Git Questions
> * Practically speaking, how does git rebase function compared to git merge?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> * When using git, what exactly do people mean when they talk about "the SHA-1"?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> What is your prefered Git workflow for a group project?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()
