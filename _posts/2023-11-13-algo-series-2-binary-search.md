---
layout: post
title: "Algo Series #2 - Binary Search"
date: 2023-11-13T05:25:32.715Z
image: ../uploads/binarysearch.jpg
title_color: "#ffffff"
caption: All I see are ones and zeros
comments: true
tags:
  - Algorithms
  - Programming
  - Searching
---
*This post is part of a series of several posts about well-known programming algorithms. To see more posts on this topic, check out the [Algorithms tag](https://jasonmauss.com/tags/#Algorithms). The source code for this post and every algorithm post can be found at my [Algorithms GitHub repo here](https://github.com/jasonmauss/Algorithms/tree/main/BinarySearch).*

### Introduction

Despite what the name might imply, the binary search algorithm is not a method for searching through ones and zeros. The algorithm gets it's name due to the "one or the other" nature of how it narrows down the possible items to search, eliminating roughly half of the remaining values each time through it's loop. To view an implementation of binary search in .NET, you can look [here](https://github.com/microsoft/referencesource/blob/master/mscorlib/system/array.cs). Binary search is around line 900 of that file.

### Purpose

The purpose behind binary search is quite simple. For finite, sorted arrays binary search will find the position in the array for the given value to search for. Some quick examples:

If your array had values like this

`[1, 2, 3, 4, 5, 6, 7, 8, 9]`

and you called binary search, passing a value of 6, it would give you the position of 6 in the array, which is 7, for a zero-based index.

Another example with not so clean linear values could be:

`[4, 10, 17, 22, 41, 50, 77, 102, 133, 196]`

where if you called binary search on it with the value of 50, you would get a return value of 5 for a zero-based index. Here's a visual representation of how binary search goes about finding the index of the value it is searching for:

![Binary Search Visualization](../uploads/binary-search-work.gif "By Mazen Embaby - Own work, CC BY-SA 4.0, https://commons.wikimedia.org/w/index.php?curid=124018514")

### The Code (JavaScript)

The three key components to implementing the binary search algorithm are:

1. A "left" value (some call this "start") that represents the smallest, or "left most" position in the array to begin searching at.
2. A "right" value (some call this "end" or "finish") that represents the largest, or "right most" position in the array to stop searching at.
3. A "middle" value that represents the middle point between left and right positions. This middle value is typically obtained by taking the floor value of left + right and dividing it by two.

Knowing these three components, let's begin writing our binary search code. Here is the beginning, just establishing what we need to create and keep track of inside the while loop that will do the searching.

```javascript
const binarySearch = (inputValuesArray, valueToFind) => {

    let leftPosition = 0;
    let rightPosition = inputValuesArray.length - 1;

    while(leftPosition <= rightPosition) {
        let middlePosition = Math.floor((leftPosition + rightPosition) / 2);

    }

};
```

Now, before we go any further, I want to discuss the unit tests we want to write for this function. There are mostly positive tests to write, but I also think this function should have some negative tests too - where the value we are trying to find doesn't exist, so we can account for that also. We also want to have at least one test where the array contains duplicates of the value we are searching for.

### Tests

Here's the code we can write for our tests. While there are some great unit testing frameworks for JavaScript, I'm just going to keep it simple and write unit test results to the console directly.

```javascript
// unit tests

const searchArraySequential = [1, 2, 3, 4, 5, 6, 7];
console.log(binarySearch(searchArraySequential, 4)); // expected: 3

const searchArrayDuplicates = [1, 2, 3, 4, 4, 5, 6, 7];
console.log(binarySearch(searchArrayDuplicates, 4)); // expected: 3 or 4

const searchArraySkippedNumbers = [4, 10, 17, 22, 41, 50, 77, 102, 133, 196];
console.log(binarySearch(searchArraySkippedNumbers, 50)); // expected: 5

const searchArrayValueDoesntExist = [10, 25, 32, 49, 55, 61, 70];
console.log(binarySearch(searchArrayValueDoesntExist, 42)); // expected: -1
```

This is not an exhaustive test for the standard binary search algorithm, but it should at least get you thinking about what to expect from the function's behavior. You could also add tests for things like searching unsorted arrays, or where the value appears first in the array, or appears last in the array just to test certain boundary conditions. But we're going to keep it simple with these tests and focus on the algorithm and finish writing the function now.

### Back to the code

Let's pick up where we left off and start writing the code that compares the current middle position's value to the value we're searching for, and adjusts the left or right position accordingly.