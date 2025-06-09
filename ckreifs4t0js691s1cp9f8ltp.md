---
title: "Guidelines for Asymptotic Notations"
seoTitle: "Guidelines for Asymptotic Notations"
seoDescription: "Learn about Asymptotic Notations and Guidelines to calculate the time complexity of a program."
datePublished: Thu Jul 22 2021 06:05:00 GMT+0000 (Coordinated Universal Time)
cuid: ckreifs4t0js691s1cp9f8ltp
slug: guidelines-for-asymptotic-notations
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1626174522528/bODxj3g-4.png
tags: cpp, programming, data-structures

---

There are some general rules to help us determine the running time of an algorithm.
We will see how to calculate running time of :

1. **If-else statements**
2. **A Loop **
3. **Nested Loops**
4. **Consecutive Statements**
5. Why do we get **Logarithmic Complexity** in a program?


**Note** : We always consider the worst case scenarios while determining the complexities of each algorithms as it will give us the maximum running time of an algorithm for large input values.

Let's say we have a program having two statements with `O(1) : Constant Time` and `O(n) : Linear Time` respectively, we will consider `O(n)` as the complexity of the whole program because we know that the program will not take more than `O(n)` time, so it will be the **Upper Bound** of the program.

For an introduction to Asymptotic Notations visit [here](https://abhishekchandra.hashnode.dev/asymptotic-notations).

### If-else statements

We first have to check the complexity of the ***condition*** inside the if statement, plus we will consider the complexity of either the *then* part or the *else* part. (whichever is greater).
```cpp
// condition statement : constant time O(1)
if( n % 2 == 0 ) // (even number)
   return true;  // then statement : constant time O(1)
else
   for(int i = 1; i <= n; i++) // else statement : linear time O(n)
      sum = sum + i;  // we get the sum of first x numbers if x is odd.
```

`Total time  = O(n)` as O(n) is the maximum time consuming statement (else statement) so the whole program will not take more than O(n) time to completely finish executing.

### Loops:
The running time of a loop is determined by the *number of times the loop is executed multiplied by the running time of the statements inside the loop.*

```cpp
// loop will execute n times
for(int i = 0; i < n; i++){
  m = m + 2;             // takes constant time, c, O(1)
}
```

`Total time = c * n = cn = O(n)`


**Q1: Will it effect the time complexity of the program, if we take `i *= 2` rather than `i++` in the update expression of `for loop`?**

*A1: We will soon find the answer. Keep reading ;)*


### Nested Loop

Here *total running time will be the product of sizes of all the loops*. <br>We have to analyse the program inside out. First we have to check from the inner most loop and it's statements, then one level up every time we have checked the complexity of the current loop.

```cpp
// outer loop exexutes n times.
for(int i = 0; i < n; i++){
   // inner loop executed n times.
   for(int j = 0; j < n; j++){
      k++;          // constant time, c , O(1)
   }
}
```

Here inner loop executes `n times` for every `i`, so Total time would be : 

`Total time = c * n * n` = cn<sup>2</sup> = O(n<sup>2</sup>)

**Q2: Will it effect the time complexity of the program, if `j` (inner loop initialisation condition) starts from `i` or `i + 1`**?

*A2: **It will not!** as we are looking for large values of n, we have to consider that loop ran for n times.*

For more information about why are we taking large values of n: [visit here](https://abhishekchandra.hashnode.dev/asymptotic-notations)

### Consecutive Statements

We just have to add the time complexity of each statements. :)

```cpp
x = x + 1;  // constant time c0

// executes n times
for(int j = 1; j < n; j++){
  m = m + 2;   // constant time c1
}

// outer loop exexutes n times.
for(int i = 0; i < n; i++){
   // inner loop executed n times.
   for(int j = 0; j < n; j++){
      k++;          // constant time
   }
}

```

`Total Time : ` c<sub>0</sub> + c<sub>1</sub>n + c<sub>2</sub>n<sup>2</sup> = O(n<sup>2</sup>)

## Why do we get **Logarithmic Complexity**?
An algorithm is `O(logn)` if it takes a constant time to cut the problem size by a fraction (usually by 1/2). Let's see an example.

```cpp
for(int i  = 1; i < n; )
   i = i * 2;
```

If we observe carefully, the value of `i` is doubling every iteration. Initially `i = 1`, in next step `i = 2`, and in following steps `i = 4, 8` and so on. Let us assume that the loop is executing some k times. At k<sup>th</sup> step 2<sup>k</sup> = n and we come out of the loop. Taking logarithm on both sides, gives 

<center>
 *log*(2<sup>k</sup>) = *logn*
<br>
 *klog2 = logn*
<br>
 *k = logn*  
<br>
</center>

`Total Time : O(logn)`

Referring to the **Q1**, the answer would be YES, changing the update condition from `i++` to `i = i * 2`, will change the time complexity of the loop to `O(logn)`.

Let's also see the below case where the time complexity is also`O(logn)`.

```cpp
for(int i = n; i >= 1;)
  i = i / 2;
```
From the above case, we can say that the logarithmic complexity comes up for decreasing sequence as well.

Another example: *binary search* 

- Look at center point in the array
- Is the element towards left or right of center?
- Repeat process with left to right part of the array until the element is found.


# Bonus

### Commonly used Logarithms

 - *log* x<sup>y</sup> = y*log*x            

 - *log* n = *log*<sub>10</sub>n

 - *log*(xy) = *log* x + *log* y

 - *log*<sup>k</sup>n = (*log*n)<sup>k</sup>

 - *log* *log* n = *log*(*log* n)

 - *log*(x / y) = *log*x - *log* y

Thank You!