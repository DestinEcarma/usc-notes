---
creation date: 2024-09-05T22:30:52
tags:
  - DSA
external links:
  - https://github.com/DestinEcarma/learning-c/tree/main/DSA/activity-12
---

# Activity 12

Create a [[Sets|set]] list of operations for a linked list. Implement the following operations:

1. `zeroSet`: creates a set with 0 elements.
2. `insertSet`: inserts an element into the set.
3. `deleteSet`: deletes an element from the set.
4. `unionSet`: creates a set that is the union of two sets.
5. `intersectionSet`: creates a set that is the intersection of two sets.
6. `differenceSet`: creates a set that is the difference of two sets.
7. `complementSet`: creates a set that is the complement of a set.
8. `isEqualSet`: checks if two sets are equal.

```c title=datatype
#define MAX 10

typedef char Set[MAX];
```

## Answer

```c title=implementation
void zeroSet(Set* set) {
	memset(*set, 0, sizeof(short) * MAX);

	/*for (int i = 0; i < MAX; i++) {*/
	/*	(*set)[i] = 0;*/
	/*}*/
}

void insertSet(Set* set, int data) {
	(*set)[data] = 1;
}

void removeSet(Set* set, int data) {
	(*set)[data] = 0;
}

Set* unionSet(Set* A, Set* B) {
	Set* result = (Set*)malloc(sizeof(Set));

	for (int i = 0; i < MAX; i++) {
		(*result)[i] = (*A)[i] || (*B)[i];
	}

	return result;
}

Set* intersectionSet(Set* A, Set* B) {
	Set* result = (Set*) malloc(sizeof(Set));

	for (int i = 0; i < MAX; i++) {
		(*result)[i] = (*A)[i] && (*B)[i];
	}

	return result;
}

Set* differenceSet(Set* A, Set* B) {
	Set* result = (Set*) malloc(sizeof(Set));

	for (int i = 0; i < MAX; i++) {
		(*result)[i] = (*A)[i] && !(*B)[i];
	}

	return result;
}

Set* complementSet(Set* A) {
	Set* result = (Set*) malloc(sizeof(Set));

	for (int i = 0; i < MAX; i++) {
		(*result)[i] = !(*A)[i];
	}

	return result;
}

bool isEqualSetSortedTest(Set* A, Set* B) {
	int i = 0;
	int j = 0;

	while (
		i < MAX && j < MAX &&
		(*A)[i] == (*B)[j]
	) {
		i++;
		j++;
	}

	return i == MAX && j == MAX;
```
