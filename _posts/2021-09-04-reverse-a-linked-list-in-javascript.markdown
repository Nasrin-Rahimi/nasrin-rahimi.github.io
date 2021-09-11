---
layout: post
title:      "Reverse a Linked List in JavaScript"
date:       2021-09-04 07:26:55 -0400
permalink:  reverse-a-linked-list-in-javascript
---

In this blog post, we are going to talk about solutions for Reverse a singly linked list in JavaScript.

The function should take one input (head of the list) and return the new head of the list.

    // Single Linked List Class
    function SinglyLinkedListNode(value) {
        this.value = value;
        this.next = null;
    }

Iterative Solution

We iterate through the list once, changing the next pointer of each node to the previous node. We should copy node.next into tmp before setting node.next to previous. 


    function reverseList(head) {
        let current = head;
        let prev , tmp;
        
        while(current) {
            tmp = current.next;
            current.next = prev;
            prev = current;
            current = tmp;
        }
        return prev;
    }

The time complexity for reverseList function is O(n) and the space complexity is O(1).

Recursive Solution

A recursive solution takes up more space since functions accumulate on the call stack.

    function recursiveReverse(head) {
    if (!head || !head.next) {
        return head;
    }
    let tmp = recursiveReverse(head.next);
    head.next.next = head;
    head.next = undefined;
    return tmp;
    }

Both of the time complexity and the space complexity for recursiveReverse function are O(n).

When recursiveReverse() reaches the end of the list, it will grab the last node as the new head and reference each node backwards.

Thanks for reading!
