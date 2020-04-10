---
layout: post
title:      "Understanding “this” in Arrow Functions"
date:       2020-04-10 01:48:18 +0000
permalink:  understanding_this_in_arrow_functions
---



Arrow function implicitly returning an object
The “this” keyword might be one of the most confusing and elusive parts of JavaScript because of its behavior in different contexts compared to other languages. This blog will explore “this” behavior in ES6 arrow functions, arrow function syntax, and implementation.
Arrow functions were created to simplify function scope and make using the “this” keyword more straightforward.
How “this” binds in ES5 code
If the “this” keyword were inside an object’s method, a function that belongs to an object, it would reference the object. If “this” refers to the method’s inner function, it would be out of scope. It would then belong to the window object.
Why does “this” bind to a window object?
The answer is pretty simple, “this” always references the owner of the function it is in. When the “this” keyword is inside of an object’s method, the function’s owner is the object. Therefore, the “this” keyword is bound to the object. Yet, when it is inside of a function, either stand-alone or within another method, it will always reference the window/global object, “this” falls out of scope.
Why does this happen?
Developers reference it as a quirk, something that isn’t exactly straightforward, meaning it doesn’t work the way you think it should. To remedy this, developers came up with arrow functions ES6!

ES6 arrow function
Let’s break down the syntax of an arrow function:
First, arrow functions need to be a function expression, you cannot put it alone like a regular function.
Parameters are then, passed inside the parenthesis like a regular function.
Next, the => indicates this is an arrow function, followed by the body of the function.

Arrow function defined with parameters.
If your function just has a single expression, you can omit the curly braces, the return keyword and write a whole function on a single line:

Single expression with implicit return
This function allows you to have an implicit return, which means the expression will be returned when calling the function without the return keyword.

Two separate arrow functions with parameters (multiple and single, respectively), and an implicit return
These functions are equivalent to:

Two separate arrow functions with parameters (multiple and single, respectively), and an explicit return
If you write a block of code inside the curly braces to contain your function’s body, even if it is just a single statement, you still have to explicitly use the return keyword if you want to return something.
To implicitly return an object, make sure to wrap the object in parenthesis:

Arrow function implicitly returned an object
Arrow functions and the “this” keyword
In ES5, working with regular functions and the “this” keyword was cumbersome and complex. We always had to keep track of “this” and bind it correctly. When working with multiple nested functions, the complexity could lead to confusion. It is much easier to use arrow functions with the “this” keyword. Arrow functions do not bind to “this” and if “this” is accessed inside the arrow function, it is taken from the outside.

The “this” keyword inside the map function binds to the person object through inheritance
In the example above, we see “this.name” inside of the “map” function. Due to the arrow function not having its own binding to “this’, it will go outside and find it. Here, it finds the doing() method, which belongs to the person object, then in this case, “this” will refer to the person object. It binds to an object like a parasite.
Otherwise, if “map” were a regular function, “this” would refer to the global object, which is the window object. Then, the return where the name is supposed to be would be “undefined” or just nonexistent.

this.name is nonexistent due to it falling out of scope
It is beneficial to use arrow functions just as a function. It has virtually replaced regular functions in ES6, there are a few exceptions of course. It shouldn’t be used as a constructor because they cannot be called with the “new” keyword.

Arrow functions cannot be used as constructors because it doesn’t respond to the “new” keyword.
When working with events, “this” value inside a function should be dynamic, so arrow functions may not be ideal.

Implementation of Arrow functions
Arrow functions are anonymous functions and their primary uses are asynchronous programming or anything that needs to be repeated over and over again such as a list. It also makes using the “this” keyword simpler by allowing it to bind easily to the primary object, like in our person example. I may add a Part II for arrow functions because there's a ton more to learn. I think I have a gift of breaking down complex concepts so that it’s easier to absorb. Researching and blogging about these concepts, then applying what I learned will only make me a better coder. So stay tuned.









