---
title: "Strings in C++"
seoTitle: "Strings in C++"
datePublished: Wed Mar 17 2021 16:46:53 GMT+0000 (Coordinated Universal Time)
cuid: ckmdog1zv01f3ils14rlhagmh
slug: strings-in-c
canonical: https://dev.to/abhishekchandra2522k/strings-in-c-6ih
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1615999521218/4anIzGsyf.png
tags: cpp, competitive-programming, string

---

Youkoso!

#### Here's Traditional Way (C Language)
 - We use _null-terminated (`\0`) character array_, although it is not technically a data type.
 - So, Operators cannot be applied to them, like assignment and comparison operators `=, <, >, <=, >=`.

```
// Declaration of character array
char s1[10], s2[10];
s1[10] = "Doge";
```
![s1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/s0c1rardwthip8zkxs54.png)

```
// Error Full Code (Don't use at home/work)
s2 = s1;
s2 > s1;
s3 = s1 + s2;
```
This code results in invalid array operations.

## Strings in C++
 - The `string` class is a expertise class of a more general template called `basic_string`.
 - Since defining a class in C++ is creating a new data type, string is derived data type.
 - This means operators can be overloaded for this class.

![Strings](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/efzcbao3d9cmc36wb73h.png)

##### syntax
```
class string{
   // Variables
   // functions
   // operators
}

string s1;
s1.function();
s1.operator(arguments);
```

string operations are safe but time consuming. So, 'char array' (speedy, less operations) concept is **not** deprecated.

`if (speed matters)` {

 Use `character array`

}`else if (safety and easy manipulation matters)` {

 Use `string` class
}

Here's why `string` is safer than character array

 - Careless programmers, can overrun to the end of 
an array that holds a null terminated (null character `\0`) string.
 - for example - *see below*
 - string class handles such issues.

```
char s3[10];
strcpy(s3,"Hello careful programmers.");
```
![s3](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1733oy61mimje3naf4ft.png)

#### String is also in STL (but concept of string is thought apart from STL concepts)
 - string is an another container class.
 - To use string class, we have to include string header class. (**not** string.h)

  - `#include<string>` (for string header class)
  - `#include<string.h>` (in C, for string functions applied on character array)

##### String class supports many constructors as follows.
 - `string()`
 - `string(const char *str)`
 - `string(const string &str)`

###### Operators
 - `=` (assignment)
 - `+` (concatenation)
 - `+=` (concatenation assignment)
 - `==` (equality)
 - `!=` (inequality)
 - `<` (less than)
 - `<=` (less than equal to)
 - `>` (greater than)
 - `>=` (greater than equal to)
 - `[]` (subscripting)
 - `<<` (insertion)
 - `>>` (extraction)

###### Mixed Operations
 - We can mix string objects with another string object or C style string.
 - C++ string can also be concatenated with character const.

###### Useful methods
 - `assign()`
 - `append()`
 - `insert()`
 - `replace()`
 - `erase()`
 - `find()`
 - `rfind()`
 - `compare()`
 - `c_str()`
 - `size()`

###### Visit : 
 - [strings.cpp](https://github.com/abhishekchandra2522k/CPPrograms/blob/master/strings.cpp)
 - [Templates in C++](https://abhishekchandra.hashnode.dev/templates-in-cpp)

ittekimasu! :)