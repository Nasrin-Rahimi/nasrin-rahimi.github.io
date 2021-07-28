---
layout: post
title:      "Time Complexity"
date:       2021-07-26 11:26:55 -0400
permalink:  time-complexity
---

What is Time Complexity?

Time complexity represents the number of times a statement is executed. The time complexity of an algorithm is NOT the actual time required to execute a particular code, since that depends on other factors like programming language, operating software, processing power, etc.

In other hand, we calculate the cost of a function, by counting the number of lines that are run in a function. The cost of performing a function varies with the size of the input, so we describe the cost in terms of the size of the input. We call this cost the “time complexity” of the function.


Big O notation is the most common metric for calculating time complexity. It describes the execution time of a task in relation to the number of steps required to complete it.

Here, we want to calculate the time it takes to check if a name exists in an array of student's name. First let’s write out the code, and then we’ll calculate the cost. Our code may look like the following:

    function arrayIncludes(array, name){
        let result;
        for(let i = 0; i < array.length; i++) {
            if (array[i] === name) {
                result = true;
            }
        }

        return !!result;
    }

    arrayIncludes(['Nasrin', 'Sara', 'Mateen'], 'Ali') => false

    arrayIncludes(['Nasrin', 'Sara', 'Mateen'], 'Nasrin') => true

In the code above, we visit each element in the array, and then we ask the question, does it equal our name. If there is no matching element, the result variable will equal undefined, to coerce that into a boolean value we use the !! operator.

Now how long does that entire procedure take?

    function arrayIncludes(array, name){
        let result;   //1
        for(let i = 0; i < array.length; i++) {   //2
            if (array[i] === name) {   //3
                result = true;   //4
            }
        }

        return !!result;   //5
    }

So first, when we ask how long a procedure takes, a shorthand is to ask how many lines of code are involved. In the above code, not including those closing brackets, it looks like the answer is five. 

Let’s take a closer look by using our function to determine if the name 'Ali' is in the array ['Nasrin', 'Sara', 'Mateen'].

    function arrayIncludes(array, name){
        let result;   //1
        for(let i = 0; i < array.length; i++) {   //2
            if (array[i] === name) {   // + 3
                result = true;   
            }
        }

        return !!result;   //6
    }

In the first line, we declare the variable let result; Then, for each element we ask if it equals 'Ali'. So we run the if expression 3 times (one for each name). Finally, we coerce the variable result to it’s boolean value, and return that value. So we would probably say there are 6 steps involved.

If let the number of names in our array be n then we can say our function runs in n + 3 time. So if we choose an array of 100 names, this takes 100 + 3 = 103 time. We call this the time complexity of the function.

Thanks for reading!



