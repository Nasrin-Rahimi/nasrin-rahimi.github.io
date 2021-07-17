---
layout: post
title:      "Error Handling In JavaScript"
date:       2021-07-16 02:26:55 -0400
permalink:  error-handling-in-javascript
---

JavaScript is a loosely-typed language. It does not give compile-time errors. So it happens to get a runtime error for accessing an undefined variable or calling undefined function etc.

JavaScript provides error-handling mechanism to catch runtime errors using try-catch-finally block.

    try
    {
        // code that may throw an error
    }
    catch(error)
    {
        // code to be executed if an error occurs
    }
    finally{
        // code to be executed regardless of an error occurs or not
    }

In try block we can use throw keyword to raise a custom error. The error will be handled by the catch block. The finally block executes regardless of whatever happens.
Let's have an input that the user can enter his/her age. We can check user's input by try block and return a proper message, if input isn't a number:


    let age = document.getElementById('age').value
    try {
        if(isNaN(age)) {
            throw 'Age must be a number!'
        }
    } catch(error) {
        message.innerText = error
    } 

We can do a custome error handling by creating a custome error object. By doing so we can pass arguments and create as many helpful properties or instance methods as we need.

    class ageError {
        constructor(age, message){
            this.age = age
            this.message = message
        }
    }

    const submitBtn = document.getElementById('submit')
    const input = document.getElementById('input')
    const message = document.getElementById('message')

    function checkAge(age) {
        if(isNaN(age)) {
            throw new ageError(age, 'is not a number!')
        } 
    }

    submitBtn.addEventListener('click', () => {
        message.innerText = ''
        
        try {
            checkAge(input.value)
        } catch(error) {
            console.log(error)
            message.innerText = `${error.age}  ${error.message}`
        }
    })

