---
layout: post
title:      "Recursion"
date:       2021-08-05 02:26:55 -0400
permalink:  recursion
---

In this blog post, I'll use the recursion technique to develop a JavaScript recursive function, which is a function that calls itself.

Introduction to Recursion

In computer science, recursion is a method of solving a problem where the solution depends on solutions to smaller instances of the same problem. Such problems can generally be solved by iteration, but this needs to identify and index the smaller instances at programming time. 

In JavaScript, a recursive function is a function that calls itself until it doesn't. And this technique is called recursion. 

For example, the function below is recursive:

    function countDown(n){
        console.log(n)
        if(n > 1){
            countDown(n -1) // recursive call
        } else {
            return true // base case
        }
    }

    countDown(5)
    // 5
    // 4
    // 3
    // 2
    // 1

You can see that in the body of the function, that the function calls itself. That part of the function is called the recursive call. You can also see that the function has a stopping point, which we call the base case. If there were no stopping point, the function would just keep going on forever. 