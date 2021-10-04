---
layout: post
title:      "Binary Search Tree in JavaScript"
date:       2021-10-01 07:26:55 -0400
permalink:  binary-search-tree-in-javascript
---

In this blog post, we talk about Binary Search Tree data structure in Javascript. 

In computer science, a binary search tree (BST), also called an ordered or sorted binary tree, is a rooted binary tree data structure whose internal nodes each store a key greater than all the keys in the node’s left subtree and less than those in its right subtree. A binary tree is a type of data structure for storing data such as numbers in an organized way.

In JavaScript a Binary Search Tree node class is like:

    // Node class
    class Node
    {
        constructor(data)
        {
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }

A node class has three properties data, left and right. Left and right are pointers to the left and right node in a Binary Search Tree. 

Now let’s see an example of a Binary Search Tree class. 

    // Binary Search tree class
    class BinarySearchTree
    {
        constructor()
        {
            // root of a binary search tree
            this.root = null;
        }
    }

Binary Search tree class, contains a private variable root which holds the root of a tree, and it's initialized to null. 

Insert data in a Binary Search Tree

    insert(data)
    {
        // Creating a node and initialising with data
        var newNode = new Node(data);
                        
        // root is null then node will
        // be added to the tree and made root.
        if(this.root === null)
            this.root = newNode;
        else
            // find the correct position in the tree and add the node
            this.insertNode(this.root, newNode);
    }
    
    // Method to insert a node in a tree
    // it moves over the tree to find the location
    // to insert a node with a given data
    insertNode(node, newNode)
    {
        // if the data is less than the node
        // data move left of the tree
        if(newNode.data < node.data)
        {
            // if left is null insert node here
            if(node.left === null)
                node.left = newNode;
            else
                // if left is not null recur until null is found
                this.insertNode(node.left, newNode);
        }
 
        // if the data is more than the node data move right of the tree
        else
        {
            // if right is null insert node here
            if(node.right === null)
                node.right = newNode;
            else
    
                // if right is not null recur until null is found
                this.insertNode(node.right,newNode);
        }
    }

In the above code there is two methods insert(data) and insertNode(node, newNode). 

insert(data) function creates a new node with a value data, if the tree is empty it add this node to a tree and make it a root, otherwise it calls insert(node, data).

insert(node, data) function compares the given data with the data of the current node and moves left or right accordingly and recur until it finds a correct node with a null value where new node can be added.

Remove a node with a given value from a Binary Search Tree

    remove(data)
    {
        // root is re-initialized with root of a modified tree.
        this.root = this.removeNode(this.root, data);
    }

    // Method to remove node with a given data
    removeNode(node, key)
    {
            
        // if the root is null then tree is empty
        if(node === null)
            return null;

        // if data to be delete is less than roots data then move to left subtree
        else if(key < node.data)
        {
            node.left = this.removeNode(node.left, key);
            return node;
        }

        // if data to be delete is greater than roots data then move to right subtree
        else if(key > node.data)
        {
            node.right = this.removeNode(node.right, key);
            return node;
        }

        // if data is similar to the root's data then delete this node
        else
        {
            // deleting node with no children
            if(node.left === null && node.right === null)
            {
                node = null;
                return node;
            }

            // deleting node with one children
            if(node.left === null)
            {
                node = node.right;
                return node;
            }
            
            else if(node.right === null)
            {
                node = node.left;
                return node;
            }

            // Deleting node with two children
            var aux = this.findMinNode(node.right);
            node.data = aux.data;

            node.right = this.removeNode(node.right, aux.data);
            return node;
        }

    }

We have two methods remove(data) and removeNode(node, data).

remove(data) is a helper function which call removeNode by passing root node and given data and updates the root of the tree with the value returned by the function.

removeNode(node, data) function searches for a node with a given data and then perform certain steps to delete it.

Deleting the leaf node – As leaf node does not have any children, hence they can be easily removed and null is returned to the parent node.

Deleting a node with one child – If a node has a left child, then we update the pointer of the parent node to the left child of the node to be deleted and similarly, if a node have a right child then we update the pointer of the parent node to the right child of the node to be deleted.

Deleting a node with two children – In order to delete a node with two children we find the node with minimum value in its right subtree and replace this node with the minimum valued node and remove the minimum valued node from the tree.

Tree Traversal

Inorder Traversal

Traverse the left subtree then visit the root, then traverse the right subtree.

    // Performs inorder traversal of a tree
    inorder(node)
    {
        if(node !== null)
        {
            this.inorder(node.left);
            console.log(node.data);
            this.inorder(node.right);
        }
    }

Preorder Traversal

Visit the root, then traverse the left subtree then , then traverse the right subtree.

    // Performs preorder traversal of a tree   
    preorder(node)
    {
        if(node !== null)
        {
            console.log(node.data);
            this.preorder(node.left);
            this.preorder(node.right);
        }
    }

Postorder Traversal

Traverse the left subtree then , then traverse the right subtree, then visit the root.

    // Performs postorder traversal of a tree
    postorder(node)
    {
        if(node !== null)
        {
            this.postorder(node.left);
            this.postorder(node.right);
            console.log(node.data);
        }
    }

To read more about Binary Search Tree, check helpful below link:

https://www.geeksforgeeks.org/implementation-binary-search-tree-javascript/

Thanks for reading!
