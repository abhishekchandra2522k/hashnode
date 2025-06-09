---
title: "Selection Sort Algorithm Explained!"
seoTitle: "Selection Sort Algorithm Explained!"
seoDescription: "Selection sort algorithm use an approach to find the max or the min element in an array at each step and then perform put it at its correct index."
datePublished: Wed Nov 30 2022 17:37:59 GMT+0000 (Coordinated Universal Time)
cuid: clb3xlh2u000308l4gppp9rzt
slug: selection-sort
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1669746424070/v_iez23WV.png
tags: sorting, blogswithcc

---

In the previous article, I explained how the [Bubble Sort algorithm](https://abhishekchandra.hashnode.dev/bubble-sort) works. Please have look at the Bubble Sort algorithm first before reading this article as it will be easier for you to learn the Selection Sort algorithm having Bubble Sort in mind. So, let's begin with this article now!

# Introduction

As we know, sorting is a process of arranging a list of items in an order, so that the items in the list are arranged either in ascending order or descending order.  To sort a list, we will see how selection sort works in this article.

In the Selection sort algorithm, we use an approach to find the *maximum* or the *minimum* element in an array at each step and perform the swap with the last or first indexed element respectively (basically to its correct position), it helps us to sort that particular element in the array. At each step, we also reduce the search space to find the max or min element in the array and to swap the elements as the array starts to sort after each step. One use case for selection sort is that it performs well with small lists/arrays. So, without further ado, let's jump right into the flow to learn Selection Sort.

# Scope

* Algorithm for Selection Sort
* Java Program for Selection Sort
* Space and Time complexity analysis

# Algorithm for Selection Sort (Ascending Order)

First, let's see, what are we going to do in the selection sort algorithm, and then we will jump right onto the how we gonna do it part. So, let's begin!

## What are we doing?

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669818314326/VA5cddYZg.png align="left")

Let's suppose, we have been given an array `[4, 3, 5, 2, 1]` (sorted array should be `[1, 2, 3, 4, 5]`). We are going to perform swaps step-by-step (swap simply means to exchange the array elements):

**Step 0:** First, we are finding the maximum element's index and then performing the swap with the last index. Here, `5` is the max element with index 2, so we swap it with the value `1` having index 4 (the last index in the current array search space).

![selection_max1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669828143494/kIcJvSo93.png align="left")

**Note:** As we have completed **Step 0**, we can see that the maximum element in the array has been shifted to the last index of the array, i.e., the last index of the array is now sorted. This also means that we will reduce our search space for the max element by 1 from the end.

**Step 1:** Now, we are finding the maximum element's index in the reduced array space and then performing the swap with the current array space's last index. Here, `4` is the max element with index 0, so we swap it with the value `2` having index 3 (the last index in the current array search space). 

![selection_max2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669828150179/pMCrNsUzi.png align="left")

**Note:** As we have completed **Step 1**,  we will reduce our search space for the max element by 1 from the end.

**Step 2:** Again, we are finding the maximum element's index and performing the swap with the current array space's last index. Here, `3` is the max element with index 1, so we swap it with the value `1` having index 2 (the last index in the current array search space).

![selection_max3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669828156456/Zq2m7ppaL.png align="left")

**Note:** As we have completed **Step 2**,  we will reduce our search space for the max element by 1 from the end.

**Step 3:** Again, we are finding the maximum element's index and performing the swap with the current array space's last index. Here, `2` is the max element with index 0, so we swap it with the value `1` having index 1 (the last index in the current array search space).

![selection_max4.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669830380442/Tc-12gur5.png align="left")

**Note:** As we have completed **Step 3**, our array is now sorted completely. We don't have to check for the remaining one element (`1`) in the array as when the (n-1) elements of the array become sorted the last element is automatically sorted. (`n: size of the array`)


Similar to the above approach, we can sort the array by finding the **minimum element** at each step and swapping it with the first index of our search space array. See the below image to understand the selection sort mechanism with a minimum element approach.

![selection_min.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669825120705/9uOU2brdB.png align="left")

Now, let's see how we can convert the above approach into an algorithm that will help us to program a solution for Selection Sorting.

## How we are doing it? (Flow Algorithm for Selection Sort (Maximum element))

* First, we have to initialize an array of elements or take user input for the array elements in the main method.
* Then, we call the `selectionSort(arr)` method (passing the `arr` as a parameter in the function), which will shift the control to the `selectionSort()` method.
* We run a for loop in the `selectionSort()` method, and iterator `i` represent our steps count, such that `0 ≤ i < n-1`, where n is the length of the array.
* We declare a `last = n - i - 1` variable that will be used to reduce our search space for finding the maximum element and swapping it with its correct position.
* We call the `max(arr, 0, last)` function, which will give us the maximum element's index in the current search space, i.e., `start = 0` and `end = last`.
* Now, we just swap the maximum element's index value with the last element.
* We repeat the above two steps at each pass until our `i < n-1`.
* In the end, the control comes back to the `main()` function, and we print the sorted array using the `Arrays.toString()` method in Java.

## Java Program for Selection Sort

<iframe style='max-width:100%; border: none; height: 375px; width: 700px;' height=375 width=700 src=https://www.interviewbit.com/embed/snippet/f63473ef19d621365faf title='Interviewbit Ide snippet/f63473ef19d621365faf' loading="lazy" allow="clipboard-write" allowfullscreen referrerpolicy="unsafe-url" sandbox="allow-scripts allow-same-origin allow-popups allow-top-navigation-by-user-activation allow-popups-to-escape-sandbox"></iframe>

[Static Code for Selection Sort Java (GitHub)](https://github.com/abhishekchandra2522k/Java-IDEA-Projects/blob/main/Algorithms/Sorting/src/SelectionSort.java)

**Note:** Selection sort is **not** a stable sorting algorithm.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669829290568/MI2zT69Ox.png align="left")

# Space and Time Complexity Analysis for Selection Sort

Recommended visiting [Asymptotic Notations](https://abhishekchandra.hashnode.dev/asymptotic-notations) and [Guidelines for Asymptotic Notations](https://abhishekchandra.hashnode.dev/guidelines-for-asymptotic-notations).

## Time Complexity for Selection Sort

**Average Case:** As we are running nested loops (one for the steps count, and one for finding the maximum element's index) for the length of the array, the average case time complexity also comes out to be **O(N<sup>2</sup>)**.

* One loop to for the steps count = O(N)
* Another loop to find the maximum element's index = O(N)

Overall complexity = O(N) \* O(N) = O(N\*N) = **O(N<sup>2</sup>)**

Best Case and Worst Case complexities also come out to be **O(N<sup>2</sup>)** as we are running the loops no matter whether it is sorted or not.

## Space Complexity for Selection sort

Space complexity for the selection sort algorithm is **O(1)**, as it is an in-place sorting algorithm and doesn't take up any extra space to sort the array.

# Outro

Thank you for reading this article, I hope that you were able to understand how selection sort algorithms work. Try to play around with the code, put debug pointers while running the program, use different input arrays, and use pen and paper to see how the algorithm works. Afterward, please leave a like and share it with your friends and family! 

Happy Coding! :))

**Reference: [Kunal Kushwaha](https://www.youtube.com/@KunalKushwaha)**
