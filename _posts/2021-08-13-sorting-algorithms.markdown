---
layout: post
title:      "Sorting Algorithms"
date:       2021-08-13 11:26:55 -0400
permalink:  sorting-algorithms
---

In computer science, a sorting algorithm is an algorithm that puts elements of a list into an order. The most frequently used orders are numerical order and lexicographical order, and either ascending or descending.

Benefits of Sorting

Certain problems become easier when our collection is sorted. For example, if we would like to see if an array includes the number two:

    let sortedArray = [-1, 1, 3, 5, 6]
    array[2]
    // 3
    // so know need to look lower
    // only need to look at indices 0 and 1

    let unsortedArray = [5, 6 -1, 1, 3]
    array[2]
    // -1
    // so guess again

Other operations, that become easier with a sorted array:

Finding the minimum of an array
Finding a maxiumum of an array
Finding the median of an array

Ok, now lets talk about how we can sort a collection of unsorted elements. For example in the below array, we want to place the numbers from lowest to highest;

    let unsortedArray = [5, 6, -1, 1, 3];

We can find the Minimum given our original array, and remove that element. Now with the new array, find the minimum again, and remove that element, and keep doing this until our unsorted array is empty. Then push these removed elements into an empty array one by one. At the end we should have a sorted array.

    function findAndRemoveMin(array) {
        let min = array[0];
        let minIndex = 0;
        for(let i = 1; i < array.length; i++) {
            if(array[i] < min){
                min = array[i];
                minIndex = i;
            }
        }

        array.splice(minIndex, 1);
        return min;
    }

    function selectionSort(array){
        let newMin;
        let sortedArray = [];
        while(array.length != 0) {
            newMin = findAndRemoveMin(array);
            sortedArray.push(newMin);
        }
        return sortedArray;
    }

What’s the big O

We have to call our findAndRemoveMin function one for each element of the array (as we remove one element each time, and keep going until the array is empty). Ok, so n times, we incur a cost of findAndRemoveMin. We know we have to call findAndRemoveMin n times in selectionSort function, So the cost of selection sort is n squared.

Note: It seems that each time we call findAndRemoveMin on a smaller array, so the cost of findAndRemoveMin shouldn’t be n each time, but rather be one less than it was previously. Let’s continue with this logic - it’s technically correct. The first time we call findAndRemoveMin the cost is n, the second time we call it the cost is n - 1, all the way down until the cost is one.

On average the cost of findAndRemoveMin is (1/2)n. This is because the first time the cost is n, and the last time it is zero. With big O we don’t consider the multipliers, so the cost of findAndRemoveMin is still n, and therefore the cost of selection sort is n^2.

Thanks for reading!







    
