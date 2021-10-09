---
layout: post
title:      "Hash Table in JavaScript"
date:       2021-10-08 08:26:55 -0400
permalink:  hash-table-in-javascript
---

Hash Table is a data structure that allow you to create a list of paired values. You can then retrieve a certain value by using the key for that value, which you put into the table beforehand.

This data structure is widely used in many kinds of computer software, particularly for associative arrays, database indexing, caches, and sets. 

The performance of a hash table depends on three fundamental factors: hash function, size of the hash table, and collision handling method.

In JavaScript, hash tables are generally implemented using arrays as they provide access to elements in constant time.

Uses of hash tables

Hash tables provide access to elements in constant time, so they are highly recommended for algorithms that prioritize search and data retrieval operations. Hashing is ideal for large amounts of data, as they take a constant amount of time to perform insertion, deletion, and search.

In terms of time complexity, the operation is 0(1). On average, a hash table lookup is more efficient than other table lookup data structures. Some common uses of hash tables are:

Database indexing
Caches
Unique data representation
Lookup in an unsorted array
Lookup in sorted array using binary search

How to implement a hash table

To implement a hash table using JavaScript, we will do three things: create a hash table class, add a hash function, and implement a method for adding key/value pairs to our table.

create the HashTable class

    class HashTable {
        constructor() {
            this.values = {};
            this.length =  0;
            this.size =  0;
        }
    }

The constructor contains an object in which we’re going to store the values, the length of the values, and the entire size of the hash table.

Simple hashing function

    calculateHash(key) {
        return key.toString().length % this.size;
    }

This function takes the provided key and returns a hash that’s calculated using an arithmetic modulus.

To read more about hash table, check below link:

https://www.educative.io/blog/data-strucutres-hash-table-javascript

Thanks for reading!
