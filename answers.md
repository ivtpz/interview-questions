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

## Front End Questions
* If you have 5 different stylesheets how would you best integrate them into the site?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()  https://www.impressivewebs.com/best-way-add-css-web-page/
  http://ryowheatley.blogspot.com/2016/12/master-vs-multiple-stylesheets-short.html
]

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


> Describe the difference between `<script>` `<script async>` and `<script defer>`.

* **Definition:**
..* Script - embed executable JavaScript, fetched & executed immediately - next line is not parsed until this one completes
..* Script Async - Continue parsing while this loads, only works with src, executes at first opportunity after it’s available, before page loads - order of async execution may change from order on page
..* Script defer - execute after the document is parsed, but before it loads. Defer tags will execute in order
* **Example:**
..* If the script is modular and does not rely on any scripts then use async.
..* If the script relies upon or is relied upon by another script then use defer.
..* If the script is small and is relied upon by an async script then use an inline script with no attributes placed above the async scripts.
* **Why:** Async helps the page load faster (by not pausing HTML parsing to download), defer does the same, but guarantees order of execution
* **References:** [Growing with the web](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)



> Why is it generally a good idea to position CSS `<link>`s between `<head>``</head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

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
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

* **Definition:**
* **Example:**
* **Why:**
* **References:** []()> What does

> { box-sizing: border-box; } do? What are its advantages?
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

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

## Testing Questions

* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

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

## Back End Questions
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

> Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* **Definition:**
* **Example:**
* **Why:**
* **References:** []()

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
