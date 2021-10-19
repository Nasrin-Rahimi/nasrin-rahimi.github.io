---
layout: post
title:      "Class Methods in Ruby"
date:       2021-10-19 03:26:55 -0400
permalink:  class-methods-in-ruby
---

In Ruby, a method provides functionality to an Object. A class method provides functionality to a class itself, while an instance method provides functionality to one instance of a class. In other word, a class method is a method that is called on the class itself, not on the instances of that class. 

For example, let's say we have a class, Person. Every individual person instance should have a name attribute. To accomplish this, we'll define an instance variable, @name and an instance method #name that exposes or reveals that variable.

    class Person

        def initialize(name)
            @name = name
            @@all << self
        end

        def name=(name)
            @name = name
        end

        def name
            @name
        end

    end

Here we have an instance variable, @name, which can be set equal to a value using the name=() method, a setter method. Then, we have a getter method name that returns the value of @name. Now, we can execute the following:

person = Person.new
person.name = "Nasrin"
person.name
  # => "Nasrin" 

Let's say we wanted to keep a counter for how many person we had in our system.