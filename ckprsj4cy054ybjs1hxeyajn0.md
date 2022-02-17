## Standard Template Library in C++

```
vector<int> LET_S;
pair<string, int> GET;
list<int> STARTED;
array<int, 3> WITH;
map<int, string> STL;
```
Still don't know what these statement do?<br>
Let's read this node to head start your journey in STL.

**Standard Template Libraries** are powerful set of [C++ template classes](https://abhishekchandra.hashnode.dev/templates-in-cpp). It contains numerous pre-defined classes and are used to make programming easier.<br>
Consider Standard Template Libraries as a helping hand for not writing codes to implement Data Structures like `Linked Lists`, `Stacks`, `Queues`,  `Trees` etc.  in every program we require them (mostly in competitive programming questions), we can use these data structures by just including a library and using a pre-defined syntax.<br>
Also, classes in Standard Template Libraries are made through [template classes](https://abhishekchandra.hashnode.dev/templates-in-cpp) so these are generic in nature.


At the core of the C++ Standard Template Libraries, these are the following three well structured components.
 - **Containers.**
 - **Algorithms.**
 - **Iterators.**

## Containers 
 - Containers are used to manage and store `collection of objects` of a certain kind.
 - Container Library in STL provide containers that are used to create data structure like arrays, linked-list, trees, etc.
 - These containers are generic in nature, they can hold elements of any data types.

#### Common Containers that replicates simple and complex data structures
   - `vector` : replicates arrays
   - `queue` : replicates queues
   - `stack` : replicates stack
   - `priority_queue` : replicated heaps
   - `list` : replicates linked list
   - `set` : replicates trees
   - `map` : associative arrays

#### Classification of containers
 - **Sequence Containers** : These containers hold linear storage of data, like arrays, linked list etc.
 - **Associative Containers** : Ordered containers like map, multimap, set, multiset are associative containers. (Ordered means the values are stored in the respective container in the same order as inputted by the user)
 - **Unordered Associative Containers** : These are similar to associative containers but have different constraints, the elements are stored unordered due to the use of hash tables while implementing these containers.

#### How to use containers?
When we use containers to implement data structures, we just have to include a header file or use the respective directive to initialise the data structure you need.
```
#include<bits/stdc++.h>
```
or you can just include a specific container header file,

```
#include<iostream>

// importing vector header file to implement vectors
#include<vector>

int main(){
 vector<int> first_vector;
 return 0;
}

// vector can be used for creating dynamic arrays of `char`, `int`, `float` and other types.

```

```
#include<iostream>

//  importing list header file to implement lists
#include<list>

int main(){
 list<int> my_list;
 return 0;
}

```


## Algorithms
 - Algorithms act on containers. They provide the means by which you will perform sorting, searching, and transforming on the contents of container.
 - Algorithms Library contains built-in functions that perform complex algorithms on the data structures. 

Example: 
 - We can reverse a range with reverse() function, sort a range with sort() function, search on a range with binary_search() and so on.

 - Algorithm Libraries provide abstraction, i.e. you don't necessarily need to know how the algorithm works.

*Sorting of a vector*

<iframe style='max-width:100%; border: none' height=375 width=700 src=https://www.interviewbit.com/embed/snippet/c259affc45a5d8bc8a31 title='Interviewbit Ide snippet/c259affc45a5d8bc8a31' loading="lazy" allow="clipboard-write" allowfullscreen></iframe>

## Iterators
 - Iterators are used to step through the elements of collection of objects. These collections can be containers or subsets of containers.
 - Iterators in Standard Template Libraries are used to point to the containers.
 - Iterators actually acts as a bridge b/w containers and algorithms.

Let's look at the above code in algorithms section for reference to iterators, <br>
sort() algorithm or function have two parameters, starting iterator `vector.begin()` and ending iterator `vector.end()` pointing to first and last element in the vector respectively, now sort() compares the elements pointed by each of these iterators and arrange them in sorted order, thus it does not matter what is the type of the container and same sort can be used on different types of containers.

#### How to declare an iterator?
*Syntax*
```
// This is an iterator of type vector
vector<int> :: iterator itr; 
// itr is the iterator
 
```
Example use of iterator:

*Printing elements of a vector*

<iframe style='max-width:100%; border: none' height=375 width=700 src=https://www.interviewbit.com/embed/snippet/7440b7182e95d1e09db9 title='Interviewbit Ide snippet/7440b7182e95d1e09db9' loading="lazy" allow="clipboard-write" allowfullscreen></iframe>

Visit [this](https://github.com/abhishekchandra2522k/CPPrograms/tree/master/Standard%20Template%20Library%20) to view some Standard Template Libraries programs.
