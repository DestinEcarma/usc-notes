---
creation date: 2024-09-05T22:40:54
tags:
  - DSA
external links:
  - https://github.com/DestinEcarma/learning-c/tree/main/DSA/activity-13
---

# Activity 13

Create a [[Sets|set]] list of operations for a [[Linked List|linked list]]. Implement the following operations:

1. `initSet`: initializes a set with 0 elements.
2. `insertFirst`: inserts an element at the beginning of the set.
3. `insertLast`: inserts an element at the end of the set.
4. `insertSorted`: inserts an element in sorted order.
5. `deleteFirst`: deletes the first element of the set.
6. `deleteLast`: deletes the last element of the set.
7. `deleteData`: deletes an element from the set.
8. `makeNull`: deletes all elements from the set.
9. `isEqualSet`: checks if two sets are equal.
	- The list is sorted
	- The list is unsorted

```c title=datatypes
typedef struct node {
	int data;
	struct node *next;
} Node, *Set;
```

## Answer

```c title=implementation
void initSet(Set* set) {
	*set = NULL;
}

void insertFirst(Set* set, int data) {
	Node* trav = *set;

	while (trav != NULL && trav->data != data) {
		trav = trav->next;
	}

	if (trav == NULL) {
		Node* newNode = (Node*)malloc(sizeof(Node));

		if (newNode != NULL) {
			newNode->data = data;
			newNode->next = *set;
			*set = newNode;
		}
	}

}

void insertLast(Set* set, int data) {
	while (*set != NULL && (*set)->data != data) {
		set = &(*set)->next;
	}

	if (*set == NULL) {
		Node* newNode = (Node*)malloc(sizeof(Node));

		if (newNode != NULL) {
			newNode->data = data;
			newNode->next = NULL;
			*set = newNode;
		}
	}
}

void insertSorted(Set* set, int data) {
	while (*set != NULL && (*set)->data < data) {
		set = &(*set)->next;
	}

	if (*set == NULL || (*set)->data != data) {
		Node* newNode = (Node*)malloc(sizeof(Node));

		if (newNode != NULL) {
			newNode->data = data;
			newNode->next = *set;
			*set = newNode;
		}
	}
}

void deleteFirst(Set* set) {
	if (*set != NULL) {
		Node* temp = *set;
		*set = (*set)->next;
		free(temp);
	}
}

void deleteLast(Set* set) {
	if (*set != NULL) {
		while ((*set)->next != NULL) {
			set = &(*set)->next;
		}

		Node* temp = *set;
		*set = NULL;
		free(temp);
	}
}

void deleteData(Set* set, int data) {
	while (*set != NULL && (*set)->data != data) {
		set = &(*set)->next;
	}

	if (*set != NULL) {
		Node* temp = *set;
		*set = (*set)->next;
		free(temp);
	}
}

void makeNull(Set* set) {
	while (*set != NULL) {
		deleteFirst(set);
	}
}

bool isEqualSetSortedTest(Set A, Set B) {
	while (A != NULL && B != NULL && A->data == B->data) {
		A = A->next;
		B = B->next;
	}

	return A == NULL && B == NULL;
}

bool isEqualSetUnsortedTest(Set A, Set B) {
	bool result = true;

	Node *outerA = A;
	Node *outerB = B;

	while (outerA != NULL && outerB != NULL && result) {
		Node *innerA = A;
		Node *innerB = B;

		while (innerA != NULL && outerB->data != innerA->data) {
			innerA = innerA->next;
		}

		while (innerB != NULL && outerA->data != innerB->data) {
			innerB = innerB->next;
		}

		result = innerA != NULL && innerB != NULL;
		outerA = outerA->next;
		outerB = outerB->next;
	}

	return result;
}
```
