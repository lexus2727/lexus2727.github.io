---
layout: post
title:      "What is "self"?"
date:       2020-04-09 21:07:13 -0400
permalink:  what_is_self
---


What is "self"?
 
self is a special  variable that points to the object that owns the currently executing code.  Ruby uses self everywhere:

* for instance variables
* for method and constant lookup.
* when defining methods, classes and modules

Every object knows itself, in every method, by the way of calling self. This is a special keyword in Ruby, that means just that: The object itself.

Let’s try that, and output self. In order to do that we need to add it somewhere inside the object. Any method would be good for that, but let’s just use the initialize method:

class Person
  def initialize(name)
    @name = name
    p self
  end
end

person = Person.new("Candice")
p person

#<Person:0x0000560720339118 @name="Candice">
#<Person:0x0000560720339118 @name="Candice">


As you can see we output the same object twice. Once in the initialize method using p self, and once in the outer scope using p person. You can also see that the cryptic looking object id is the same for both instances. So we can know it’s indeed the very same object.

