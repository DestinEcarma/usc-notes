---
creation date: 2024-08-23T22:44:07
tags:
  - DSA
---

# Array Implementation

Arrays in **data structures** help solve some high-level problems like the "longest consecutive subsequence" program or some easy tasks like arranging the same things in ascending order. The concept is to collect many objects of the same kind (S, n.d.).

Based on the definition of the array implementation of list write the code of the ff:

```c title=datatype
define MAX 10

typedef struct {
	int elems[MAX];
	int count;
} List;
```

# What is an Array?

==An array is a variable containing multiple homogeneous values==. Homogeneous values mean the same values. This means if we are declaring an array of integer type then only integer values will be there in an array. We can’t store floating values along with it (Shiksha, n.d.).

==An array is a linear data structure that collects elements of the same data type and stores them in contiguous and adjacent memory locations==. Arrays work on an index system starting from $0$ to $(n-1)$, where n is the size of the array (S, n.d.).

# References

1. S, R. A. (n.d.). Arrays in Data Structure: A Guide With Examples. Simplilearn.com. Retrieved August 23, 2024, from https://www.simplilearn.com/tutorials/data-structure-tutorial/arrays-in-data-structure
2. Shiksha. (n.d.). Implementing Arrays in C Programming. Shiksha.com. Retrieved August 23, 2024, from https://www.shiksha.com/online-courses/articles/arrays-in-c-programming
