---
layout: post
title:      "Understanding Recursion, Simply"
date:       2020-07-14 16:03:16 -0400
permalink:  understanding_recursion_simply
---




 This can be better seen on medium: https://medium.com/@lexus2424/understanding-recursion-simply-4fa57bcda5b
 
I think the concept of recursion can be difficult for new developers to understand and implement. As a new developer, I totally understand. So, I decided to write a blog that breaks down recursion in a way anyone can learn and understand. The point of this blog is once you learn the basics you can build on it, as you gain more experience through practice. I’ll go over what exactly recursion is and how to implement it using examples.
What is recursion?
Simply put, recursion is a function that calls itself inside its body until it’s stopped by a condition. Recursive functions are used to break down heavy data structures into smaller ones. Generally used in sorting and binary searches.
Image for post
A recursive function always has a condition to stop calling itself, otherwise, it will call itself indefinitely. I’m going to demonstrate this using an if statement.
Image for post
JavaScript recursive examples
Suppose you need to develop a function that counts down from a specified number to 1. It’s always best to write a pseudocode before beginning to write your code. It’s a good way to keep track of your progress as you work through a problem. So, if you get stuck you can retrace your steps.
To count down from 10 to 1, recursively, you can:
show the number 10
call the function e.g, countDown(9) that shows the number 9
then call the countDown(8) that shows the number 8
continue until you call countDown(1) and stops at 0
create a condition that will stop the function once it reaches 0
Image for post
Output:
Image for post
Using “null” in recursion
The name of the function is a reference to the actual function object. Don’t forget functions are objects. If somewhere in the code, the function is set to null, the recursive function will stop working because we would be calling the function on an empty value. If this should happen you will get a TypeError such as this:
Uncaught TypeError: countDown is not a function
Here is an example of how you can use null in recursion
Image for post
Output:
Image for post
So, what I did was set function f to the variable countDown. Then towards the end of the code, I assigned countDown to the variable funCountDown, which will hold the current function object. Next, I reassigned countDown to null, so that it points to an empty value. Then I called funCountdown(10) and I received the above output. The concept here is if you assign the variable to a function so that it simply references the function object, you can later reassign the function to a new variable and set the previous one to null, so that the value is completely empty.
Calculate sums using recursion
Given a number 456, calculate the sum of the digits 4 +5+6 = 15.
To apply the recursive technique, you can use the following steps:
f(456) = 6 + f(45)
f(45) = 5 + f(4)
f(4) = 4 + 0 (stop here)
So,
f(456) = 6 + f(45)
f(456) = 6 + 5 + f(4)
f(456) = 6 + 5 + 4
Notice how we’re using the function object to break down the data structure to add the sum.
This example shows the sum() recursive function:
Image for post
How this works:
The num % 10 returns the remainder of the number after divided by 10, 456%10 = 6.
The Math.floor(num/10) returns the whole part of the num/10, Math.Floor(456/10) = 45
The if(num === 0) is a condition that stops calling the function.
Summary
So the only way to understand recursion is through Practice Practice Practice! Start simply as we’ve done here then gradually work through harder problems, ensuring to write down pseudocode to give yourself a blueprint to reference. As you work with recursion remember a recursion function is a function that calls on itself until it’s stopped by a condition. If your call stack size has exceeded its limit, then it’s a sign that the function at some point was unable to stop. So make sure the function always has a condition to stop.
References:
Learn and Understand Recursion in JavaScript
I’ll walk you through two popular JS recursion examples in 10 minutes so you can finally understand how recursion works…
codeburst.io
How to Use Recursion in Your JavaScript Code - dummies
You can call functions from outside of the function or from within other functions with JavaScript. You can even call a…
www.dummies.com
A Quick Intro to Recursion in Javascript
The function calls itself until someone stops it. Recursion can feel difficult to new developers. Perhaps that's…
www.freecodecamp.org




Candice Parker
veryfine69
