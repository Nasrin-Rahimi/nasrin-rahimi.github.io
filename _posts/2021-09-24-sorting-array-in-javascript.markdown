---
layout: post
title:      "Sorting an Array in JavaScript"
date:       2021-09-24 09:26:55 -0400
permalink:  sorting-an-array-in-javascript
---

The sort() method in javascript allows you to sort elements of an array in place. As a result, the sort() method changes the positions of the elements in the original array.

The time and space complexity of the sort cannot be guaranteed as it depends on the implementation.

By default, the sort() method sorts the array elements in ascending order with the smallest value first and largest value last.

For example:

    const months = ['March', 'Jan', 'Feb', 'Dec'];
    months.sort();
    console.log(months);

The output is:

    output: Array ["Dec", "Feb", "Jan", "March"]

Let's look at another example:

    let numbers = [0, 1 , 3, 10, 30 ];
    numbers.sort();
    console.log(numbers);

The output is:

    [0, 1, 10, 3, 30];

But wait, it's not the answer we want!

The above output is because, the sort() method casts elements to strings and compares the strings to determine the orders. The sort() method places 10 before 3 because the string “10” comes before “3” when doing a string comparison.

To fix this, The sort() method accepts an optional argument which is a function that compares two elements of the array.

    array.sort(comparefunction)

The compare function of the sort() method accepts two arguments and returns a value that determines the sort order. 

    function compare(a,b) {
        // ...
    }

The sort() method will sort elements based on the return value of the compare() function with the following rules:

1- If compare(a,b) is less than zero, the sort() method sorts a to a lower index than b. 

2- If compare(a,b) is greater than zero, the sort() method sort b to a lower index than a

3- If compare(a,b) returns zero, the sort() method considers a equals b and leaves their positions unchanged.

    let numbers = [0, 1 , 3, 10, 30 ];
    numbers.sort( function( a , b){
        if(a > b) return 1;
        if(a < b) return -1;
        return 0;
    });

    console.log(numbers);

Output is:
    
        [ 0,  1, 3, 10, 30 ]

We can define the comparison function using the arrow function syntax:

    let numbers = [0, 1 , 3, 10, 30 ];
    numbers.sort((a,b) => {
        if(a > b) return 1;
        if(a < b) return -1;
        return 0;
    });
    
Since the elements of the array are numbers, the simplest way is:

    let numbers = [0, 1, 3, 10, 30];
    numbers.sort((a, b) => a - b);

Sorting an array of strings

Consider the array below:

    let colors = [
        'green', 'red', 'blue', 'yellow'
    ];

To sort the elements of the colors array in ascending order alphabetically, you use the sort() method without passing the compare function as shown in the following example:

    colors.sort();

Output is:

    ['blue', 'green', 'red', 'yellow']

To sort the colors array in descending order, we need to change the logic of the compare function and pass it to the sort() method as the following example.

    colors.sort((a, b) => {
    if (a > b)
        return -1;
    if (a < b)
        return 1;
    return 0;
    });

This is the basic of sorting in javascript. To read more about sorting, check helpful below links:

https://www.javascripttutorial.net/javascript-array-sort/

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort

Thanks for reading!



