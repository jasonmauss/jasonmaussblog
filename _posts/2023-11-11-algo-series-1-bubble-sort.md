---
layout: post
title: "Algo Series #1 - Bubble Sort"
date: 2023-11-11T21:38:11.502Z
image: ../uploads/bubble-sort-bubbles.jpg
title_color: "#ffffff"
caption: We're not sorting actual bubbles, but it would be cool if you could!
comments: true
tags:
  - Algorithms
  - Programming
  - Sorting
---
*This post is the first in a series about well-known programming algorithms. To see more posts on this topic, check out the Algorithms tag.*

### Introduction

I thought it would be proper to begin a series of posts on algorithms by discussing the bubble sort algorithm since it is widely considered to be one of the more simple algorithms (sorting or otherwise) you will encounter when you are studying the topic. Bubble sort is not the most efficient sorting algorithm that exists and many popular modern languages use more efficient algorithms. For example, Java uses dual-pivot Quicksort for primitive values, and Python uses TimSort, which is a combination of both merge sort and insertion sort. In fact, if you want to check out the C# (.NET) "Introspective Sort" implementation, you can read the source code [here](https://github.com/microsoft/referencesource/blob/master/mscorlib/system/array.cs) (search for "IntrospectiveSort").

In fact, I would describe the overall purpose of learning bubble sort as more of an academic programming exercise and a mental warm-up before tackling more advanced or complex sorting algorithms. With that in mind, let's dive right in.

### Purpose

To begin, I think it's important that we state the objective of what we are trying to accomplish with this code. Hopefully most (or all) of you have figured out we need to sort some values. If we go a step further we might wonder *what kind of values* or asked differently, *what kind of data structures* does bubble sort ... sort? The generic answer to that question is that bubble sort works on arrays and linked lists, or any data structure where adjacent elements can be compared and swapped - if they are out of order - going from left to right.

For example, an array of values like this

`[6, 2, 1, 4, 5, 3]`

becomes this

`[1, 2, 3, 4, 5, 6]`

after sorted using the bubble sort algorithm.