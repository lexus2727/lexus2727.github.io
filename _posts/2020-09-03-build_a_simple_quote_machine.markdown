---
layout: post
title:      "Build A Simple Quote Machine"
date:       2020-09-04 01:07:20 +0000
permalink:  build_a_simple_quote_machine
---


I decided to create a simple javascript quote machine to practice basic concepts I'll be demonstating live on my new channel on Youtube called <devCandice>. I started off by creating a folder in File Explorer which acted as my workspace on VS code. i keep a folder for skill building projects in a folder called "code" and projects in a folder called "projects". I then create a folder structure in VS code, index.html, style.css, and index.js. I created the the html boiler plate first. I then created a div container for the button that will generate the quotes through an event listener and an output where the quotes will be displayed. I attached ids to both, "btn" and "output", respectively. Now that the html structure was created, I went on to my css folder and styled the container by centering the application and putting a border around it. I also styled the button, gave it a nice background color and styled the foreground to black. After the styling was finished I went on to give some functionality. I first selected the button and stored it to the variable, btn and selected it by id. Then I selected the output and stored the output by the id, output. Lastly I stored the quotes in an array, and called it quote.

So once my variables were set up. I created an event listerner and appended it to my btn object as a click function. I also wanted to have the quotes randomly selected so I created a variable called randomQuote and set quote array and within that array I wrote Math.floor and passed Math.random in as argument and multiplied it by the length of the array. What happens is Math.random always returns a floating number,so Math.floor will turn it into an integer which will choose the largest integer equal to or less than the length of the array. When the user clicks on the button a quote selected randomly from the array and displayed where I set up a div for output in html.

I will provide a link to my page on Medium where I can create a visual presentation. It's hard to do that on this platform.

Happy Coding

Candice
