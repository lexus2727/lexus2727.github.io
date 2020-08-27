---
layout: post
title:      "Building a React Weather App"
date:       2020-08-27 15:45:35 -0400
permalink:  building_a_react_weather_app
---


The content of your blog post goes here.

I decided to exercise my react skills with a basic weather app. I learned how by watching a tutorial and then trying it out on my own. The set up was pretty simple. I created three children components and one parent component. The three children components are Forecast.js which is responsible rendering the current weather conditions, Form.js, form so user can input the city and country to see current conditions, and Heading.js displays the heading and subheading in the browser. The parent component I used was App.js to render the three children to the browser.

I used OpenWeatherMap.org as my external API. Using that service was really easy. All I was required to do was register on the site and subscribe for an API Key .They sent the key directly to my email. 

I also added a submit button called "Get Weather" in the Form component, which when clicked triggers the getWeather(), which grabs the values of city and country and then when a request is made to the api those values are passed in as well. Then like a machine we wait for a response and if the values are inputted correctly on the form we get a response with values to all the parameters I preselected from OpenWeatherMap.org such as values for my chosen city and country, humidity, temperature in farenheit, humidity, pressure, a weather icon, and description. I even added on an error that when a person fills out the form incorrectly the error is captured in the console and I added a message to tell the user to fill out the form correctly. If the user leaves an input blank the error then console.logs and the form will not submit, so that will let the user know to fill in the blanks.

The link to my live app is https://lexus2727.github.io/forecast_app/ .

Candice





