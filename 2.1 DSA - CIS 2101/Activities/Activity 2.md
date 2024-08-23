---
creation date: 2024-08-18T00:31:28
tags:
  - DSA
links:
  - "[[Linked List]]"
  - "[[Traversal]]"
  - "[[Pointer To Pointer To Node]]"
  - "[[Look-Ahead Technique]]"
---

# Activity 2

> A linked list can be implemented in computer’s memory WITH or WITHOUT header. A header cell is a dynamically allocated node or cell that will not store any data. It is used to have uniformity in accessing and hence making the code concise but with an additional storage overhead.

```c title=datatype
typedef struct node {
	int data;
	struct node *next;
} *List;
```

**Given the definition of data type List, write the code of the following functions:**

-  Initialize the list to be empty (***With header cell*** vs. ***Without Header Cell***)
	1. `initListWithHeader()` - *The function will initialize the given list to be empty by letting the given list point to a dynamically allocated header cell. See illustration above.*
	2. `initListNoHeader()` - *The function will intialize the given list to be empty by simply making it NULL. See illustration above.*
- `Function insertLast()` the function will insert a given element at the last position of the given list.

	Write the code of function insertLast() using the following versions:
	1. List with header cell: This list variation will use a look-ahead technique for traversal.
	2. List without header cell:
		- Version 1: Using a [[Pointer To Pointer To Node|PPN]] to traverse
		- Version 2: Using a [[Look-Ahead Technique]] to traverse.
- Function `deleteElem()` the function will delete the first occurrence of the given element from the list.

	Write the code function `deleteElem()` using the following versions:
	1. List without header cell using PPN.
	2. List without header cell using look-ahead technique.

## Answer

- Initialize the list to be empty (***With header cell*** vs. ***Without Header Cell***)

```c title=header
void initListWithHeader(List*);
void initListNoHeader(List*);
```

```c title=declaration
void initListWithHeader(List *L) {
	*L = (struct node*)malloc(sizeof(struct node))

	if (*L != NULL) (*L)->next = NULL;
}

void initListNoHeader(List *L) {
	*L = NULL;
}
```

- `Function insertLast()` the function will insert a given element at the last position of the given list.

```c title=header
void insertLast(List*, int); // With PPN
void insertLast(List, int); // With look-ahead technique
```

```c title=declaration
// Using PPN to traverse
void insertLast(List* L, int data) {
	if (L != NULL) {
		while (*L != NULL) L = &(*L)->next;

		struct node* newNode = (struct node*)malloc(sizeof(struct node));

		if (newNode != NULL) {
			newNode->data = data;
			newNode->next = NULL;

			*L = newNode;
		}
	}
}

// Using a look-ahead technique to traverse
void insertLast(List L, int data) {
	if (L != NULL) {
		struct node* newNode = (struct node*)malloc(sizeof(struct node));

		if (newNode != NULL) {
			while (L->next != NULL) L = L->next;

			newNode->data = data;
			newNode->next = NULL;
			L->next = newNode;
		}
	}
}
```

- Function `deleteElem()` the function will delete the first occurrence of the given element from the list.

```c title=header
void deleteElem(List*, int); // With PPN
void deleteElem(List, int); // With look-ahead technique
```

```c title=declaration
// List without header cell using PPN
void deleteElem(List* L, int elem) {
	if (L != NULL) {
		while (*L != NULL && (*L)->data != elem) L = &(*L)->next;

		if (*L != NULL) {
			List temp = *L;
			*L = temp->next;

			free(temp);
		};
	}
}

// List without header cell using look-ahead technique
void deleteElem(List L, int elem) {
	while (
		L != NULL && \
		L->next != NULL && \
		L->next->data != elem
	) L = L->next;

	if (L->next != NULL) {
		List temp = L->next;
		L->next = temp->next;

		free(temp);
	}
}
```
