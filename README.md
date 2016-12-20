# JavaScript Interview Questions

## Factual JS Fundamental Questions
* What is a “closure” in JavaScript?
* What is the difference between undefined and not defined in JavaScript?
* How do you empty an array in JavaScript?
* How do you check if an object is an array?
* What is the difference between classical inheritance and prototypal inheritance?
* What is the event loop in JavaScript and how does it handle synchronous and asynchronous functions?
* Explain event delegation
* Explain how this works in JavaScript
* Explain how prototypal inheritance works
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: function foo(){ }();. What needs to be changed to properly make it an IIFE?
* What's a typical use case for anonymous functions?
* How do you organize your code? (module pattern classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between: function Person(){} var person = Person() and var person = new Person()?
* What's the difference between .call and .apply?
* Explain Function.prototype.bind.
* When would you use document.write()?
* What's the difference between feature detection feature inference and using the UA string?
* Explain Ajax in as much detail as possible.
* What are the advantages and disadvantages of using Ajax?
* Explain how JSONP works (and how it's not really Ajax).
* Have you ever used JavaScript templating?
* Explain "hoisting".
* Describe event bubbling.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
* What is an example of an immutable object in JavaScript?
* What are the pros and cons of immutability?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop? What is the difference between call stack and task queue?
* Explain the differences on the usage of foo between function foo() {} and var foo = function() {}
* Why is extending built-in JavaScript objects not a good idea?
* What is the difference between == and ===?
* Explain the same-origin policy with regards to JavaScript.
* Why is it called a Ternary expression what does the word "Ternary" indicate?
* What is "use strict";? what are the advantages and disadvantages to using it?
* Is JavaScript statically or dynamically typed? Is JavaScript strongly typed or loosely typed? What do those terms mean? 
* Practically speaking, what's a "declarative" language?
* Is JavaScript a functional language? What does it mean for a language to be "functional"?
* What's an IIFE in JS? When would you use it? 
* What is JSONP

## Opinion based
* Why would you use JS?
* Why did you use AngularJS for your project?
* Why should we consider using React?
* If you were building Twitter what tech stack might you use?
* Why do you want to work at X company?  

## Data Structures Questions
* What is the average and worst-case time complexity of access, search, and insertion for common data structures? For each answer, briefly explain why.
* What's a "tuple"? What's a "triple"? What's the difference between a tuple and a set?

## Front End Questions
* If you have 5 different stylesheets how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces what would you do?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?
* What does a doctype do?
* What's the difference between full standards mode almost standards mode and quirks mode?
* What's the difference between HTML and XHTML?
* Are there any problems with serving pages as application/xhtml+xml?
* How do you serve a page with content in multiple languages
* What are data- attributes good for?
* Describe the difference between a cookie sessionStorage and localStorage.
* Describe the difference between `<script>` `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head>``</head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
* What is progressive rendering?
* Have you used different HTML templating languages before?
* What is the difference between classes and IDs in CSS?
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose and why?
* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* Describe BFC(Block Formatting Context) and how it works.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system and if so what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does * { box-sizing: border-box; } do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative fixed absolute and statically positioned element?
* The 'C' in CSS stands for Cascading. How is priority determined in assigning styles (a few examples)? How can you use this system to your advantage?
* What existing CSS frameworks have you used locally or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so when and what techniques did you use?
* Is there any reason you'd want to use translate() instead of absolute positioning or vice-versa? And why?
* What's the difference between an "attribute" and a "property" in HTML?
* Difference between document load event and document DOMContentLoaded event?
* Why is it in general a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What are some ways you may improve your website's scrolling performance?
* In the MVC design pattern what's M stands for?
* Explain the difference between layout painting and compositing.
* Traditionally why has it been better to serve site assets from multiple domains?
* What is the difference between display: none and visibility: hidden?
* What are some ways to make a page SEO friendly
* What is the difference between document load and document ready?
* Describe the MVC pattern
* Explain the differences between React and Angular.

## Testing Questions

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?
* What tools would you use to find a performance bug in your code?
* Present a quick overview of TDD.

## Back End Questions

* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling Websockets and Server-Sent Events?
* What are HTTP methods? List all HTTP methods that you know and explain them.
* Describe server response code 200.
* Describe server response code 201.
* Describe server response code 204.
* Describe server response code 301.
* Describe server response code 400.
* Describe server response code 404.
* Describe server response code 409.
* Describe server response code 500.
* What are some advantages of CDNs? Disadvantages?
* What is a reverse proxy?
* Why Functional Programming matters? When should a functional programming language be used?
* Pro and cons of mutable and immutable values.
* What are the tradeoffs of client-side rendering vs. server-side rendering?
* How would you manage the migration of a project from MySQL to PostgreSQL?
* How is Lazy Loading achieved? When is it useful? What are its pitfalls?
* In which case would you use a document database like MongoDB instead of a relational database like MySQL or PostgreSQL?
* What's a rebase?
* What is the biggest difference between Agile and Waterfall?
* When is a cache not useful or even dangerous?
* What is the difference between emergent design and evolutionary architecture?
* Scale out vs scale up: how are they different? When to apply one when the other?
* What's Two Factor Authentication? How would you implement it in an existing web application?
* Explain the basic structure of a MIME multipart message when used to transfer different content type parts. Provide a simple example.
* Explain the difference between stateless and stateful protocols. Which type of protocol is HTTP? Explain your answer.
* Describe the key advantages of HTTP/2 as compared with HTTP 1.1.
* What is a “MIME type” what does it consist of and what is it used for? Provide an example.
* What are the main differences between a document database and a SQL database? Which would you consider "more efficient"?
* Give a brief analogy explaining how computer memory works to a beginning programmer.
* Describe the benefits of Redis.
* Describe the benefits of Elasticsearch
* How do you allow CORS requests?

 
## Git Questions
* Practically speaking, how does git rebase function compared to git merge?
* When using git, what exactly do people mean when they talk about "the SHA-1"? 
