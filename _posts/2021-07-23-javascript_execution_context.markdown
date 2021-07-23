---
layout: post
title:      "JavaScript Execution Context"
date:       2021-07-23 08:26:55 -0400
permalink:  javascript-execution-context
---

Before learning about Execution Context, we should learn about scope in JavaScript!

Scope is the concept of where something is available. In JavaScript, scope is defined by where declared variables and methods are available within our code.

Global Scope  
If a variable or function is not declared inside a function or block, it's' in the global scope.
        
Function Scope
Variables and Function declared in function, has function scope.

Block Scope
Variables and Function declared in a block by curly braces, has block scope.

Variables declared with var keyword, are not block-scoped, It means we can access to those variables outside of the block :

    if (true) {
        var myVar = 42;
    }
    myVar; // => 42

variables declared with const and let are block-scoped :

    if (true) {
        const myVar = 42;
        let myOtherVar = 9001;
    }
    
    myVar;        // Uncaught ReferenceError: myVar is not defined
    myOtherVar;   // Uncaught ReferenceError: myOtherVar is not defined
    
Variables created without a const, let, or var keyword are always globally-scoped, regardless of where they sit in your code.
        
    if (true) {
        lastName = 'Rahimi';
    }
    lastName;   // => "Rahimi"

In general, it's best practice to make variables and functions available only where they're needed — and nowhere else. Making a variable available in places that shouldn't have access to it, can only lead to bad things and make your debugging process more complex.
        
Inside the new function's body, in addition to variables and functions declared in that function, we also have access to variables and functions declared in the outer scope. 
    
    const globalVar = 1;
    function firstFunc () {
        const firstVar = 2;
        return firstVar + globalVar;
    } 
    firstFunc();  // => 3
    
A function has access to all variables and functions declared in its outer scope. In the other hand, All variables and functions declared in outer scopes are available in inner scopes via the scope chain. 

The scope chain only goes in one direction. An outer scope does not have access to things declared in an inner scope. 
    
When our JavaScript code is run in the browser, the JavaScript engine actually makes two separate passes over our code :
        
- Compilation Phase
- Execution Phase
    
In Compilation Phase the engine steps through our code line-by-line:
        
When it reaches a variable declaration:

- Allocates memory and sets up a reference to the variable's identifier (myVar).

When the engine encounters a function declaration, it does three things:
        
- Allocates memory and sets up a reference to the function's' identifier (`myFunc`)
 
- Creates a new execution context with a new scope.
 
- Adds a reference to the parent scope (the outer environment) to the scope
  chain, making variables and functions declared in the outer environment
  available in the new function's' scope.
        
In Execution Phase, The JavaScript engine again steps through our code line-by-line, but this time it actually runs our code, assigning values to variables and invoking functions.

For example if we have:

    const myVar = 42;
    myVar;    // => 42

During the compilation phase, a reference to the identifier myVar is stored in memory. The variable isn't yet assigned a value, and the second line (myVar;) is skipped over entirely because it isn't a declaration.

During the execution phase, the value 42 is assigned to myVar. When the engine reaches the second line, it sees the identifier myVar and resolves it to a value through a process known as identifier resolution. The engine first checks the current scope to see if myVar has been declared in it. If it finds no declaration for myVar in the current scope, the engine then starts moving up the scope chain, checking the parent scope and then the parent scope's parent scope and so on, until it finds a matching declared identifier or reaches the global scope. If the engine traverses all the way up to the global scope and still can't find a match, it will throw a ReferenceError and inform you that the identifier is not declared anywhere in the scope chain.
    
Thanks for reading!
    
        