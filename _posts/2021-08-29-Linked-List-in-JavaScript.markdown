---
layout: post
title:      "Linked List in JavaScript"
date:       2021-08-29 08:26:55 -0400
permalink:  linked-list-in-javascript
---

In this post, we will be implementing the LinkedList data structure in Javascript. 

In computer science, a linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Instead, each element points to the next. 

LinkedList is a dynamic data structure, as we can add or remove elements at ease, and it can even grow as needed. 

There are two types of linked list: singly linked list and doubly linked list.

Each node in a singly-linked list contains not only the value but also a reference field to link to the next node.

Let’s see an example of a Singly Linked List Node: 

    // User defined class node
    class Node {
        constructor(element)
        {
            this.element = element;
            this.next = null
        }
    }

We define a class Node having two properties: element and next. Element holds the data of a node while next holds the pointer to the next node, which is initialized to the null value. 

Now, let’s see an implementation of the Linked List class: 

    // linkedlist class
    class LinkedList {
        constructor()
        {
            this.head = null;
            this.size = 0;
        }
    }

Linked List class has two properties: head and size, where the head stores the first node of a List, and size indicates the number of nodes in a list. 

Let’s implement needed functions for linked list class:

1- add(element) – It adds an element at the end of the list.

In the order to add an element at the end of the list we consider the following : 

-If the list is empty then add an element and it will be head.
-If the list is not empty then iterate to the end of the list and add an element at the end of the list.

    //add element to the end of linked list
    add(element) {
        //create a new node
        let node = new Node(element);

        //if list is empty, add element and make it head.
        if(this.head == null){
            this.head = node;
        } else {
            let current = this.head;

            while(current.next) {
                current = current.next;
            }
            //add node
            current.next = node;
        }
        this.size++;
    }

2- insertAt(element, index) – It inserts an element at the given index in a list. 

In order to add an element at the given index of the list we consider three conditions as follows: 

-If the index is zero we add an element at the front of the list and make it head
-If the index is the last position of the list we append the element at the end of the list
-If the index is between 0 or size – 1 we iterate over to the index and add an element at that index

    // insert element at the position index of the list
    insetAt(element, index) {
        if(index < 0 || index > this.size) {
            return console.log("Please enter a valid index!");
        } else {
            let node = new Node(element);

            if(index == 0) {
                node.next = this.head;
                this.head = node;
            } else {
                let curr = this.head;
                let prev;
                let i = 0;

                 // iterate over the list to find the position to insert
                while (i < index) {
                    prev = curr;
                    curr = curr.next;
                    i++;
                }

                // adding the element
                node.next = curr;
                prev.next = node;
            }
            this.size++;
        }
    }

3- removeFrom(index) – It removes and returns an element from the list from the specified index 

In order to remove an element from the list we consider three conditions: 

-If the index is 0 then we remove the head and make the next node head of the list
-If the index is size – 1 then we remove the last element from the list and make prev the last element
-If it’s in between 0 to size – 1 we remove the element by using prev and the current node.

    removeFrom(index) {
        if(index < 0 || index > this.size) {
            return console.log("Please enter a valid index!");
        } else {
            let prev, curr, i = 0;
            curr = this.head;

            if(index == 0) {
                this.head = curr.next;
            } else {
                while (i < index) {
                    prev = curr;
                    curr = curr.next;
                    i++;
                }
                prev.next = curr.next;
            }
            this.size--;
            return curr.element;
        }
    }

4- removeElement(element) – This method removes element from the list. It returns the removed element, or if it’s not found it returns -1. 

    removeElement(element){
        let current = this.head;
        let prev = null;

        while(current != null) {
            if(current.element == element) {
                if(prev == null){
                    this.head = current.next;
                } else {
                    prev.next = current.next;
                }
                this.size--;
                return current.element;
            }
            prev = current;
            current = current.next;
        }
        return -1;
    }

Let’s declare some helper methods which are useful while working with LinkedList. 

1- indexOf(element) – it returns the index of a given element if the element is in the list. If the element isn't in the list, it return -1.

    indexOf(element) {
        let count = 0;
        let current = this.head;

        while(current != null) {
            if(current.element == element) {
                return count;
            }
            count++;
            current = current.next;
        }

        //element not found
        return -1;
    }

2- isEmpty() – it returns true if the list is empty. 

    isEmpty(){
        return this.size == 0;
    }

3- listSize() – It returns the size of list 

    listSize(){
        return this.size;
    }
    
4- printList() – It prints the contents of the list. 
we can iterate over the entire list and concatenate the elements of each node and print it.

    printList() {
        let current = this.head;
        let list = "";

        while(current) {
            list += current.element + " ";
            current = current.next;
        }

        return list;
    }

Implementation

Now, let’s use the LinkedList class and its different methods described above. 

    //Create an object for the linked list
    let linkedList = new LinkedList();

    console.log(linkedList.isEmpty());

    // adding element to the list
    linkedList.add(10);

    linkedList.printList();

    console.log(linkedList.listSize());

    // adding more elements to the list
    linkedList.add(20);
    linkedList.add(30);
    linkedList.add(40);
    linkedList.add(50);

    linkedList.printList();

    console.log("is element removed ?" + linkedList.removeElement(50));

    linkedList.printList();

    linkedList.insertAt(60, 2);

    console.log("is List Empty ? " + linkedList.isEmpty());

    console.log(linkedList.removeFrom(3));

    linkedList.printList();

Output:

    true
    10 
    1
    10 20 30 40 50 
    is element removed ?50
    10 20 30 40 
    is List Empty ? false
    30
    10 20 60 40

To read more about Linked List in JavaScript:

https://www.geeksforgeeks.org/implementation-linkedlist-javascript/

Thanks for reading!




 





