## Asymptotic Notations

The objective of this node is to explain Analysis of Algorithms and Asymptotic Notations i.e. **Big-O, Omega-Ω, and Theta-Θ.** These topics are the most basic foundation for Data Structures and Algorithms. 

## Analysis of Algorithms
The idea of _analysis of algorithms_ is to compare algorithms mainly in terms of running time and space consumed. <br> For example,
To go from city 'M' to city 'N', there can be many ways to carry-out this task: by *flight*, by *bus*, by *train* and also by *bicycle*. Depending on the accessibility and convenience, we choose the one that suits us. Similarly, in computer science we have various algorithms available for solving a same problem, for example we can solve sorting problem by many algorithms like `selection-sort`, `bubble-sort`, `merge-sort`  and *many more* but we will choose the one with lesser complexity. (Best algorithm for sorting is `quick-sort` with complexity `O(nlog(n))` ) <br>
This concludes that Analysis of Algorithm should be used in determining which method is more efficient and also which method is good in terms of time and space consumed.

Prior to learning Asymptotic Notations, Let's see what is ***rate of growth*** of an algorithm.

**Rate of growth** is nothing but the rate at which the run time complexity of the algorithm increases as a function of the input.<br>
Let's suppose we have to purchase a laptop and a mouse. If someone asks you what are you purchasing, then in general you will say buying a laptop and ignore buying the mouse part. This is because, cost of laptop is too big compared to cost of mouse. So, we can say

`Total Cost = cost_of_laptop + cost_of_mouse`

`Total Cost ≈ cost_of_laptop (approximately)`

For the above mentioned example, we can represent the cost of laptop and cost of mouse as a function and for a given function, we can ignore the lower order terms (that are relatively insignificant for large value of input size, n). Let us consider another example in terms of algebra, let n<sup>4</sup>, n<sup>2</sup>, 100n and 5 are individual costs of some function, here we can approximate this function to n<sup>4</sup> i.e. the highest rate of growth.


*n<sup>4</sup> + n<sup>2</sup> + 100n + 5 ≈ n<sup>4</sup>*

Here's the list of most common rate of growths.

| Time Complexity      | Name | Example     |
| :---        |    :----:   |          ---: |
| 1      | Constant       | accessing an array element |
| log(n)   | Logarithmic        | finding an element in a *sorted* array    |
| n   | Linear        | finding an element in a *unsorted* array    |
| nlog(n)      | Linear Logarithmic       | sorting n items with *divide-and-conquer* (Merge Sort) |
| n<sup>2</sup>   | Quadratic        | shortest path between two nodes in a graph    |
| n<sup>3</sup>   | Cubic        | matrix multiplication   |
| 2<sup>n</sup>      | Exponential       | tower of hanoi problem |

Before going to Asymptotic Notations, We also need to know about Types Of Analysis.
### Types of Analysis
If we have to analyse an algorithm, we need to know on what inputs the algorithm takes less time, and on what inputs the algorithm is taking more time. That means we can represent algorithms with multiple expressions: one for the case where it takes *less time* and other for the case where it takes *more time*. <br>
In general, when the algorithm takes less time it is called as the ***best case*** and when the algorithm takes more time than it is called as the ***worst case***. 
To analyse an algorithm we need some kind of syntax and that forms the base for asymptotic analysis / notation. 
There are three types of analysis:
 - **Worst Case** 
  - defines the input for which algorithm takes longest time to execute.
  - algorithm runs slower.
  - algorithm which executes maximum number of steps on input data of size n.

- **Best Case**
  - defines the input for which algorithm takes lowest time to execute.
  - algorithm runs fastest.
  - algorithm which executes least number of steps on input data of size n.

- **Average Case**
  - provides a prediction about the running time of the algorithm.
  - assumes that the input is random.
  - algorithm which performs average number of steps on input data of size n.


`Lower Bound <= Average Time <= Upper Bound`

<br><br>

# Asymptotic Notations

Asymptotic Notations is having an expressions for the best, average and worst cases, for all the three cases we need to identify the upper and lower bounds. To represent these upper and lower bounds we need some kind of syntax and that is the following discussion. Let us assume that for a given algorithm, it can be represented in the form of function *f(n)*.

## Big - O Notation : 
This notation gives the ***tight upper bound*** of the given algorithm / function *f(n)*. It is represented as 

`f(n) = O(g(n))`.

It means, for larger values of n, the *upper bound* of function *f(n)* is a function *g(n)*. <br>
Here *upper bound* means, value of f(n) cannot exceed g(n) after a particular value of n. (represented as n<sub>0</sub> in the graphical approach). <br>
Let's see this with a graphical approach.


![asymptotic_notations-1.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1625574434388/c5xYTEjgFV.jpeg)

After *n = n<sub>0</sub>*, value of g(n) is always greater than or equal to the given algorithm's rate of growth f(n). 


Also, for example, if *f(n)* = n<sup>4</sup> + 100n + 50 is the given algorithm, then n<sup>4</sup> is *g(n)*. That means, *g(n) = n<sup>4</sup>* gives the maximum rate of growth for *f(n)* at larger values of n. 

O-Notation can be also be defined as **O(g(n))** = { **f(n)** : there exists positive constant c and n<sub>0</sub> such that* ` 0 ≤ f(n) ≤ cg(n)` *for all  n ≥ n<sub>0</sub> }. 


Our objective is to get smallest rate of growth g(n) which is greater than or equal to f(n)'s rate of growth.<br>
Generally we discard lower values of n. That means the rate of growth at lower values of n is not important. In the graph, n<sub>0</sub> is the point from which we need to consider the rate of growths for a given algorithm. Below n<sub>0</sub> the rate of growths could be different.

#### Some Big - O Examples:


1. 
 **f(n) = n<sup>2</sup> + 1**

  n<sup>2</sup> + 1 ≤ 2n<sup>2</sup>, for all n ≥ 1

 Therefore, n<sup>2</sup> + 1 = O(n<sup>2</sup>), with c = 2 and n<sub>0</sub> = 1

2. 
**f(n) = 2n<sup>3</sup> - 2n<sup>2</sup>**

  2n<sup>3</sup> - 2n<sup>2</sup> ≤ 2n<sup>3</sup>, for all n ≥ 1

 Therefore, 2n<sup>3</sup> - 2n<sup>2</sup> = O(2n<sup>3</sup>), with c = 2 and n<sub>0</sub> = 1

There is one more thing related to values of n<sub>0</sub> and c, that is, there is no isolated set of values for n<sub>0</sub> and c in finding the asymptotic bounds. Let us see an example, 
100n + 5 = O(n). For this function, there can be multiple values for n<sub>0</sub> and c, giving us an asymptotic solution / bound.

**Solution 1 **: 100n + 5 ≤ 100n + n = 101n, for all n ≥ 5, n<sub>0</sub> = 5 and c = 101. <br>
**Solution 2 **: 100n + 5 ≤ 100n + 5n = 105n, for all n ≥ 1, n<sub>0</sub> = 1 and c = 105.

Both possibilities are correct.

**Note :** Most of the time we are interested in knowing the Big - O Notation i.e. Tight Upper Bound of an algorithm because it allows us to estimate weather an algorithm is feasible for our application or not, by telling us that this algorithm will not take more than such-and-such amount of memory or time when run on an input of size n. 

## Omega - Ω Notation : 

This notation gives the ***tight lower bound*** of the given algorithm / function *f(n)*. We can represent it as 

`f(n) = Ω(g(n))`

It means, for larger values of n, g(n) is the *lower bound* of function f(n). <br>
Here *lower bound* means, rate of growth of *f(n)* is always greater than or equal to the rate of growth of function *g(n)* after a particular value of n i.e. n<sub>0</sub>. <br>
Let's see this with a graphical approach.


![asymptotic_notations-2.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1625827947954/nqxScttcq.jpeg)

After n = n<sub>0</sub>, value of g(n) is always smaller than or equal to the given algorithm's rate of growth f(n). 

Ω Notation can also be defined as **Ω(g(n))** = { **f(n)** : there exists positive constants n<sub>0</sub> and c such that* ` 0 ≤ cg(n) ≤ f(n)` * for all n ≥ n<sub>0</sub> }. 

Here, our objective is to get largest rate of growth g(n) which is less than or equal to f(n)'s rate of growth. g(n) is asymptotic lower bound for the given algorithm's rate of growth f(n).

#### Some Ω Examples :
1. **f(n) = 5n<sup>2</sup>**

  ∃ (there exists) c, n<sub>0</sub>, such that: 0 ≤ cn ≤ 5n<sup>2</sup>  => c = 1 and n<sub>0</sub> = 1

 Therefore, 5n<sup>2</sup> = Ω(n<sup>2</sup>)

2. 2n = Ω(n), n<sup>3</sup> = Ω(n<sup>3</sup>), logn = Ω(logn)

**Note : **  Lower bounds are of great use as well. Lower bounds can give information about whether we can improve our algorithm or is it feasible. We can also know that our algorithm is optimal, if our lower bound is equal to the upper bound. 

## Theta - Θ Notation : 

This notation gives a range of upper bound and lower bound and determines whether the upper bound and lower bound of the given algorithm are same. The average running time of an algorithm is always between the **lower bound** (*Omega - Ω*) and **upper bound** (*Big - O*) of the function. If the upper bound and lower bound of a function gives the same result (rate of growth) then Theta - Θ will also have the same rate of growth. 

For example, assume f(n) = 10n + n, then its tight upper bound is O(n) and the lower bound is Ω(n). 
In this case, rate of growths in the best case and worst case are same. As a result, the average case will also be the same. 
If for a given algorithm, the rate of growths O and Ω are not same then the rate of growth for Θ may not be same. In this case, we have to consider all possible time complexities and take average of those. (for example, *quick sort* average case gives Θ(nlogn) complexity)

Let us also see this in a graphical approach.

![asymptotic_notations-3.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1625828191290/0lp6yHxKk.jpeg)

After n = n<sub>0</sub>, the value of f(n) is always between c<sub>2</sub>g(n) and c<sub>1</sub>g(n). 

Θ Notation can also be defined as **Θ(g(n))** = { **f(n)** : there exists positive constants c<sub>1</sub>, c<sub>2</sub>, and n<sub>0</sub> such that*  0 ≤ c<sub>1</sub>g(n) ≤ f(n) ≤ c<sub>2</sub>g(n) , for all n ≥ n<sub>0</sub> }. g(n) is an asymptotic tight bound for f(n).

Θ(g(n)) is a set of functions with same order of growth as g(n).

#### Some Θ Examples:

1. **Prove n ≠ Θ(n<sup>2</sup>)**
 
 c<sub>1</sub>n<sup>2</sup> ≤ n ≤  c<sub>2</sub>n<sup>2</sup>, only holds for n ≤ 1 / 
 c<sub>1</sub>

 Therefore, n ≠ Θ(n<sup>2</sup>)

2. **Prove 6n<sup>3</sup> ≠ Θ(n<sup>2</sup>)**
 c<sub>1</sub>n<sup>2</sup> ≤ 6n<sup>3</sup> ≤  c<sub>2</sub>n<sup>2</sup>, only holds for n ≤ c<sub>2</sub> / 6

 Therefore, 6n<sup>3</sup> ≠ Θ(n<sup>2</sup>)

#### Why is it called Asymptotic Notations?
For all the three notations, O, Ω, Θ, in every case for a given function f(n) we are trying to find other function g(n) which approximates f(n) at large values of n. That means, g(n) is also a *curve* which approximates f(n) at large values of n. 

In mathematics, we call such curves as **asymptotic curves**. In other terms, g(n) is the asymptotic curve for f(n). For this reason, we call algorithm analysis as **asymptotic analysis** and notations as **asymptotic notations**

### Properties of Notations:
 - **Transitivity** : f(n) = Θ(g(n)) and g(n) = Θ(h(n)), then f(n) = Θ(h(n)). Valid for O and Ω as well.
 - **Reflexivity** : f(n) = Θ(f(n)). Valid for O and Ω as well.
 - **Symmetry** : f(n) = Θ(g(n)) if and only if g(n) = Θ(f(n)).
 - **Transpose symmetry** : f(n) = O(g(n)) if and only if g(n) = Ω(f(n)).

<br>
# Bonus :

### Master Theorem for Divide and Conquer

All divide and conquer algorithms works by dividing the problem into sub-problems, each of which is part of the original problem and then we perform some additional work to compute the final answer. As an example, *merge sort* algorithm operates on two sub problems, each of which is half the size of the original problem and then performs O(n) additional work for merging the sub-problems.

This gives the running time of the equation : 

 `T(n) = 2T(n / 2) + O(n)`  

Master theorem can be used to determine the running time of divide and conquer algorithms. For a given algorithm, first we try to find the recurrence relation of the problem. If the recurrence relation is of the below form then we can directly give the answer without fully solving it. 

If the recurrence relation is of the form, ** T(n) = aT(n / b) + Θ(n<sup>k</sup>log<sup>p</sup>n)**, where a ≥ 1, b > 1, k ≥ 0 and p is a real number, then:

1. If a > b<sup>k</sup>, then T(n) = Θ(n<sup>log<sup>a</sup><sub>b</sub></sup>)

2. If a = b<sup>k</sup>
  
 a. If p > -1, then T(n) = Θ(n<sup>log<sup>a</sup><sub>b</sub></sup>log<sup>p+1</sup>n).<br>
 b. If p = -1, then T(n) = Θ(n<sup>log<sup>a</sup><sub>b</sub></sup>loglogn).<br>
 c. If p < -1, then T(n) = Θ(n<sup>log<sup>a</sup><sub>b</sub></sup>)

3. If a < b<sup>k</sup>

 a. If p ≥ 0, then T(n) = Θ(n<sup>k</sup>log<sup>p</sup>n) <br>
 b. If p < 0, then T(n) = O(n<sup>k</sup>)


Thank You!