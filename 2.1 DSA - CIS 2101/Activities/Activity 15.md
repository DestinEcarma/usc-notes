---
creation date: 2024-09-14T22:37:03
tags:
  - DSA
external links:
  - https://github.com/DestinEcarma/learning-c/tree/main/DSA/activity-15
---

# Activity 15

Create a [[Sets|set]] list of operations for a [[Linked List|linked list]]. Implement the following operations:

1. `unionSetOrderedTest`: creates a set that is the union of two sets.
  - The list is sorted
2. `unionSetUnorderedTest`: creates a set that is the union of two sets.
  - The list is unsorted

```c title=datatypes
typedef struct node {
  int data;
  struct node *next;
} Node, *Set;
```

## Answer

```c title=implementation
// Change the value depending on how big
// the number will be, if the number is
// 1024 then this means we need at least
// 128 bytes, the formula is simple
// $size = N / 8$ rounded up.
#define MAX_INT_UNORDERED_TEST = 8

Set unionSetOrderedTest(Set A, Set B) {
	Set result = NULL;
	Set* tail = &result;

	int previousData = (A->data < B->data) ? A->data - 1 : B->data - 1;

	while (A != NULL && B != NULL) {
		int data;
		Set* curr;

		if (A->data < B->data) {
			data = A->data;
			curr = &A;
		} else {
			data = B->data;
			curr = &B;
		}

		Node* temp = (Node*)malloc(sizeof(Node));

		if (temp != NULL && previousData != data) {
			temp->data = data;
			temp->next = NULL;

			*tail = temp;
			tail = &temp->next;
		}

		if (A->data == B->data) {
			A = A->next;
		}

		previousData = data;
		*curr = (*curr)->next;
	}

	Set rest = (A != NULL) ? A : B;

	while (rest != NULL) {
		Node* temp = (Node*)malloc(sizeof(Node));

		if (temp != NULL && previousData != rest->data) {
			temp->data = rest->data;
			temp->next = NULL;

			*tail = temp;
			tail = &temp->next;
		}

		previousData = rest->data;
		rest = rest->next;
	}

	return result;
}

Set unionSetUnorderedTest(Set A, Set B) {
	Set result = NULL;
	Set* tail = &result;

	// Not the most efficient method in terms of space.
	// Time complixity $O(1)$.
	unsigned char set[MAX_INT_UNORDERED_TEST] = {};

	while (A != NULL) {
		Node* temp = (Node*)malloc(sizeof(Node));

		int setIndex = A->data / 8;
		int setPlacement = A->data % 8;

		if (temp != NULL && (set[setIndex] >> setPlacement & 1) == 0) {
			temp->data = A->data;
			temp->next = NULL;

			*tail = temp;
			tail = &temp->next;

			set[setIndex] |= 1 << setPlacement;
		}

		A = A->next;
	}

	while (B != NULL) {
		Node* temp = (Node*)malloc(sizeof(Node));

		int setIndex = B->data / 8;
		int setPlacement = B->data % 8;

		if (temp != NULL && (set[setIndex] >> setPlacement & 1) == 0) {
			temp->data = B->data;
			temp->next = NULL;

			*tail = temp;
			tail = &temp->next;

			set[setIndex] |= 1 << setPlacement;
		}

		B = B->next;
	}

	return result;
}
```
