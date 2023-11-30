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