# Data Stuctures
## Title: Comparative Analysis of: Stacks, Heaps, Maps
*    **Name**: Joe Tolley
*    **Course/Semester/Section**: CSE 397 Professional Career Projects: Spring 2026: Online
*    **Instructor**: Brother Clements
*    **Date**: 06/18/2026

## Summary: 
This is an analysis of three common data-structures
## Introduction: 
Heaps, Stacks, and Maps were all researched in order to compare and contrast the differing structures.
## Overview: 
Data structures can vary by traits, speed, efficiency, and any number of factors that help to determine which one is correct for you. Knowing their purpose and usage will help a developer choose the best option for the project.
## Strength and Weakness: 
*    Stacks are Last-In-First-Out (LIFO), they are perfect for recursion and able to go from base case to final answer simply and efficiently. An issue is that they can overflow and with two many instructions or too little memory, data can be lost. Using a stack as a queue is probably not a good idea as starvation (process never processed) can occur and usually we think of a queue as FIFO. 
*    Heaps are similar to Binary Search Trees. The main difference is they are best geared for finding min and max values in O(1) time. BST's on the other hand take O(log n) but they have other improvements that heaps cannot match, mainly able to traverse and find values quickly. Heaps are great for priority queues and can be used to do the next most important thing at a time. 
*    Maps are similar to what they sound like. They have keys assigned to values, allowing for O(1) search time. They can be heavier than an array though. So if fast lookup isn't the need, they might not be the best option. 
# Useage and Applicability: 
*    Stacks are the perfect choice for recursion, they are also the best at the undo operation. It's easy and efficient to add or take away from the end of a stack.
*    Heaps are great for prioritizing tasks. If an urgent task were to be added they can naturally process it next rather than waiting for its place in a queue. An issue that might occur is when a low-priority task never gets reached due to higher prioritized requests never ceasing.
*    Maps are the best at searching using a key. A key is able to retrieve the associated value(s) attached. For instance, account management is a perfect example. A username can be associated with a specific account of information, another username to another account. Pulling up a car's specs based on it's VIN number is another example.
# Comparison: 
*    Stacks can be compared to queues, the difference being that they do the last inserted process rather than the one that was there longest. Programs and function calls are built like this, where if we call a function we would want the result immediately to return to the caller, which might be needed for another function that called it. A dynamic array allows for easy searching by index, and a dequeue gets its name from being double ended, it is essentially a combination of a queue and a stack. 
*    Heaps are great at prioritizing a min or max value, but order is not gauranteed quite as well as a BST. Trees have different features and the features for a heap might not be ideal compared to AVL trees or BST's. They are great for doing the next most important task each time.
*    Maps are great at looking up values but it also requires the most resources. Picking out a student out of 100,000 using their ID is perfect use. If looking to just process the first 100 items, maps are not a suitable replacement for a queue or other ordered structure. Other comparable structures are BST's or AVL trees which can maintain balance and order at a slight cost of searching speed. 
# Summary: 
The best option is dependent on what you are wanting to do. There is no ultimate structure, but for a particular purpose, there are certainly better types than others. In RxNow, using a Map is the natural usage simply because account management is a crucial feature. It is geared to the user who likely is not interested in their particular id number compared to the account of information they are seeking. One could say it uses a priority queue that tracks the most time sensitive refills, sending out notifications when a medication gets closer towards running out. A particular system likely has components of all three types of data structures analyzed here.
# References:
    1. ChatGPT
    2. Wikipedia
    3. geeksforgeeks.org
    4. w3schools.com
    5. stackoverflow.com
