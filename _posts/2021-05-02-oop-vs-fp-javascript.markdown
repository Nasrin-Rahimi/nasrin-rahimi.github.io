---
layout: post
title:      "Object-oriented programming vs Functional Programming with Javascript"
date:       2021-05-02 12:48:55 -0400
permalink:  Object-oriented programming vs Functional Programming with Javascript
---

First, let’s get a brief overview on what OO and FP actually are.

Object-oriented programming
According to Wikipedia, OOP “is a programming paradigm based on the concept of “objects”, which may contain data, in the form of fields, often known as attributes; and code, in the form of procedures, often known as methods. OOP tries to model real-world objects.

There are four principal/pillars of OOP:
    Encapsulation
    Abstraction
    Inheritance
    Polymorphism

For learning more about OOP in JavaScript please check the link below:

https://dev.to/bhaveshdaswani93/object-oriented-programing-in-javascript-3bp0

Functional Programming
In any program there is two core thing data and behavior. Data could be array, object,hashmap etc. Data can be in any form. Behavior is function that perform operation on data. Functional programming says that data and behavior(function) are two different thing. they should be kept separate. It simply says that you pass data to function it will process it and return new object.

Functional programming is all about separation of concerns.It's all about packaging our code into separate chunks so that everything's is well organized in each part of our code.Functional programming says that data and behavior(function) are two different thing. they should be kept separate. The core pillar of functional programming is pure function.

For learning more about FP in JavaScript please check the link below:

https://dev.to/bhaveshdaswani93/functional-programming-in-javascript-59e2

OOP organizes the code as a unit. Here the unit or the object contains the information and operation that belong to same concept. 

FP consider data and operation as two different thing. It is all about avoiding side effect and writing pure functions.Functions should not modify its outer world and its return value depends on the argument provided. 

Both OOP and FP are paradigm that is a design pattern for solving the common problem that is to make our code clear and under-stable, easy to extend, easy to maintain, memory efficient and dry.

Difference Between FP and OOP

FP is stateless means it does not modify the state of the program by return new state every time in immutable fashion while OOP is statefull, its method changes the state of its properties.
FP is about having pure function that has no side effects while OOP has side effect as it modify its state.

FP is declarative it focuses on what need to be done while OOP is imperative it focuses on how the things should be done.

It is not necessary to use only one paradigm at a time we can combine them and use the power of both paradigms. For example in react app for statefull component we use class component(OOP) and for stateless component that is which mainly deal with view part was in functional component (before hooks were introduced).

If you have few things that requires lot of operation lot of little functions applied to it then FP is good options. Functional programming works really well for high performance and processors as you can run it on multiple processors simultaneously.

If you have too many things like characters in game and few operation then OOP is good choice

Thanks for reading!

Sources:

https://en.wikipedia.org/wiki/Object-oriented_programming

https://medium.com/@sho.miyata.1/the-object-oriented-programming-vs-functional-programming-debate-in-a-beginner-friendly-nutshell-24fb6f8625cc

https://dev.to/bhaveshdaswani93/oop-vs-fp-with-javascript-39jf

