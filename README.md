#Front-end Job Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
* How many resources will a browser download from a given domain at a time?
  * What are the exceptions?
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* Describe how you would create a simple slideshow page.
* What tools do you use to test your code's performance?
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.

#### HTML Questions:

* What does a `doctype` do?

> The doctype declaration tells the browser which version of HTML the page is using (i.e. 4.01 strict, 4.01 transitional, HTML5, etc). If no doctype declaration exists, the browser will render the page in quirks mode rather than standards mode.

> Modern browsers don't care about the exact doctype, all it's needed for is to trigger standards mode. This is why the HTML5 doctype is so simple: <!DOCTYPE html> There's no need for a specific version today or in the future because all we're doing is telling the browser to operate in standards mode.

* What's the difference between standards mode and quirks mode?

> Quirks mode is used by browsers to render (mostly) legacy content that was developed in the pre-standards era. The most prominent example probably being the IE box model bug which calculates the width of a box differently than the CSS spec. Because IE5 (and prior versions) were so prominent, a lot of CSS was written in a way to accommodate IE's non-standard implementation.

* What's the difference between HTML and XHTML?
* Are there any problems with serving pages as `application/xhtml+xml`?
* How do you serve a page with content in multiple languages?
* What kind of things must you be wary of when design or developing for multilingual sites?
* What are `data-` attributes good for?
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

#### CSS Questions:

* What is the difference between classes and ID's in CSS?

> IDs should only appear once in a page's markup, classes can appear as many times as you'd like. An ID's properties as specified in CSS will also take precendence over a class, even if the class appears after the ID and has more selector specificity. For example, given the following html:

```html
<div class="person">
  <p class="person-name" id="brian">Brian Rhea</p>
</div>
<div class="person">
  <p class="person-name" id="adrian">Adrian Beltre</p>
</div>
```

> It's perfectly fine to reuse `.person` and `.person-name` multiple times. If we had goofed and used `#brian` on Adrian's `<p>` giving us two occurences of that id, the page would still render perfectly fine, the browser isn't going to complain, crash, or do anything noticeable to the user. But, `getElementByID('brian');` would be unreliable if you were to try and target that element by the ID.

> As far as how the CSS would behave, one might expect that the following code would result "Brian Rhea" being bold, black text, because those values are set after the ID with more specificity and would therefore override it.

```css
#brian {
  color: #f00;
  font-weight: 400;
}
.person .person-name {
  color: #000;
  font-weight: 700;
}
```

> But that's not the case. If the ID and class are on the same element, the ID always wins (256 chained classes used to override an ID, [but that bug has been fixed](http://codepen.io/chriscoyier/pen/lzjqh)).

* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?

> Resetting is a little bit of a nuclear option in that it targets every single html element and reduces it to scratch. No margin, no padding, no border, nothing. It's helpful because you're starting from the same place in every browser, but it removes some inherently sensible properties such as resetting the `<sub>` element's `vertical-align` property to `baseline` rather than the default `sub`.

> Normalizing holds on to some reasonable defaults and tries to get you to common ground across all browsers without being as dramatic as a full reset.

> That said, I've used Eric Meyer's reset css in personal projects in the past because – in my experience – the instances where resetting creates more work than it had saved are few and far between. But, all of my recent projects have used Bootstrap as the underlying front-end framework, and BS uses normalize which is fine by me. I'm not dogmatic on this one.

* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Any familiarity with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

* Explain event delegation

> Event delegation allows you to assign event listeners to the parent of child elements, so that you don't have to add listeners to every single node that should trigger the event's behavior.

> Take the following code for example:

```html
<ul class="ski-resorts">
  <li><a class="resort" id="vail" href="#">Vail <em>$$$$</em></a></li>
  <li><a class="resort" id="copper-mountain" href="#">Copper Mountain <em>$$$</em></a></li>
  <li><a class="resort" id="eldora" href="#">Eldora <em>$</em></a></li>
</ul>
```

> If I want to trigger a function whenever a link with `.resort` is clicked, thanks to event delegation I'm in business with the following bit of jQuery:

```javascript
$('.resort').click(function(){
  // do some stuff
});
```

> Even if the user clicks on one of those `<em>` tags, the event bubbles up to the listener on the `.resort` class.

> You can see this in action by modifying that bit of jQuery to:

```javascript
$('.resort').click(function(e){
  console.log(e.target);
});
```

> When you click on the name of the ski resort, the `<a>` element gets printed out in the console; when you click on a dollar sign, only the `<em>` element is printed because that is the child node that was clicked.

* Explain how `this` works in JavaScript
* Explain how prototypal inheritance works
* How do you go about testing your JavaScript?
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or `undeclared`?
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
* What's a typical use case for anonymous functions?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
* What's the difference between `.call` and `.apply`?
* Explain `Function.prototype.bind`.
* When would you use `document.write()`?
* What's the difference between feature detection, feature inference, and using the UA string?
* Explain AJAX in as much detail as possible.
* Explain how JSONP works (and how it's not really AJAX).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built in JavaScript objects not a good idea?
* Difference between document load event and document ready event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, `"buzz"` at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* Can you explain the difference between `GET` and `POST`?
* Can you explain the difference between `GET` and `HEAD`?

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](http://twitter.com/paul_irish) [@bentruyman](http://twitter.com/bentruyman) [@cowboy](http://twitter.com/cowboy) [@ajpiano](http://twitter.com/ajpiano)  [@SlexAxton](http://twitter.com/slexaxton) [@boazsender](http://twitter.com/boazsender) [@miketaylr](http://twitter.com/miketaylr) [@vladikoff](http://twitter.com/vladikoff) [@gf3](http://twitter.com/gf3) [@jon_neal](http://twitter.com/jon_neal) [@sambreed](http://twitter.com/sambreed) and [@iansym](http://twitter.com/iansym).

It has since received contributions from [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).
