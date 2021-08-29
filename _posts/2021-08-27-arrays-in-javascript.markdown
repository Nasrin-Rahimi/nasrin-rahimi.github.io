---
layout: post
title:      "Arrays in JavaScript"
date:       2021-08-27 07:26:55 -0400
permalink:  arrays-in-javascript
---

In the last post, we talked about how data structure used for associating and organizing information.

If we have a lot of related data, it's best to represent it in a related system. Imagine that we're working on a school class application that has to represent the student names. We could do that as follows:

    const firstStudent = 'Nasrin';
    const secondStudent = 'Ali';
    const thirdStudent = 'Sarah';
    const fourthStudent = 'David';

We've represented all four pieces of data, but they aren't related in any meaningful way. 

    function printStudentNames (first, second, third, fourth) {
        console.log("Student Names:", first, second, third, fourth);
    }

    printStudentNames(firstStudent, secondStudent, thirdStudent, fourthStudent);
    // LOG: Student Names: Nasrin Ali Sarah David
    // => undefined 

That's so much typing! There are much, much better ways to keep organize data in JavaScript. Let's learn about one of the most common: the Array.

Create Arrays

An Array is a list, with the items listed in a particular order, surrounded by square brackets ([]):

    ['This', 'is', 'an', 'array', 'of', 'strings.'];
    // => ["This", "is", "an", "array", "of", "strings."] 

The members or elements in an Array can be data of any type in JavaScript:

    ['Hello, world!', 42, null, NaN];
    // => ["Hello, world!", 42, null, NaN] 

Elements in arrays will always appear in the same order. The Array [1, 2, 3] is different from the Array [3, 2, 1].





