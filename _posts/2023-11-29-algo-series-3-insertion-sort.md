---
layout: post
title: "Algo Series #3 - Insertion Sort"
date: 2023-11-29T05:01:00.499Z
image: ../uploads/insertionsort.webp
title_color: "#ffffff"
caption: The original Mario Bros is still the best. Fight me.
comments: true
tags:
  - Algorithms
  - Sorting
  - Programming
---
The discussion of algorithms continues with **Insertion Sort**, the third overall and the second sorting algorithm covered after starting off with bubble sort. Much like bubble sort and selection sort, insertion sort is a simple, easy to understand sorting algorithm that requires very little code to implement. Keep reading to learn how it works and follow along with a code example of how to implement it as well as a discussion of when it might be the ideal sorting algorithm to use in your own code.

### Introduction

Insertion sort works by building the end result (typically an array or list of some kind) one item at a time by comparing the value the data structure will be sorted by. Just as with other simple sorting algorithms, it's not particularly efficient with a large set of values, but does shine in certain optimal scenarios, which we will cover later. 

For a visual demonstration of insertion sort, here's a quick graphic to help with the concept

![A visual demonstration of the Insertion Sort algorithm](../uploads/insertion-sort-example-300px.gif "Swfung8, CC BY-SA 3.0 <https://creativecommons.org/licenses/by-sa/3.0>, via Wikimedia Commons")

As you can see from the graphic above, insertion sort iterates over the list, from beginning to end, shifting certain portions of the sorted list depending on where the current value needs to be inserted at. These iterations continue until the end of the list is reached and all sorting has completed. For each item that gets removed to be inserted somewhere else, the *already sorted* portion of the list is checked from largest value to smallest, to determine which position the removed item should be inserted at.

### The Code (JavaScript)

Let's start off by composing our method signature and the beginning of the function, and then we'll prepare some tests. We will start our outer loop with our position variable `i` at 1, not 0. This is because the first element will get sorted automatically as we start making our comparisons and sorting the list items. We will continue comparing the list items until we reach the end of the array, so our while loop condition is `i < unsortedArray.length` .

```javascript
const InsertionSort = (unsortedArray) => {

    let i = 1;
    while(i < unsortedArray.length) {
        
    }
};
```

Tests

We don't need a particularly large number of tests for the purposes of testing this code. I'm going to go with three tests:

* Sequential numbers out of order
* Sequential numbers out of order that contain negative numbers
* Non-sequential numbers out of order that contain duplicate values

Here's the code for ours tests

```javascript
// unit tests

// Sequential numbers out of order
const array1 = [5,2,7,4,3,1,6];
InsertionSort(array1);
console.log(array1); // [1,2,3,4,5,6,7]

// Sequential numbers out of order that contain negative numbers
const array2 = [-1,-2,4,0,3,5,2,1];
InsertionSort(array2);
console.log(array2); // [-2,-1,0,1,2,3,4,5]

// Non-sequential numbers out of order that contain duplicate values
const array3 = [61,25,10,55,49,32,70,61];
InsertionSort(array3);
console.log(array3); // [10,25,32,49,55,61,61,70]
```

After I've completed all of the posts about sorting algorithms, I think I'll revisit them with a post where we performance test them all against each other and find the sweet spot where each one performs best.

### Back to the code

Now that we have our tests ready, it's time to complete writing the function.