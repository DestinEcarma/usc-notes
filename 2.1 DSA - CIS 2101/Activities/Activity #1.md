---
creation date: 2024-08-18T00:20:41
tags:
  - DSA
links:
  - "[[Pointer To Pointer To Node]]"
---

# Activity #1

Create a function to insert a new element at the end of a linked list. The function should handle the case where the element does not yet exist.

**Function Header**

```c title=header
void insertLast(List*, int)
```

**Declaration**

```c title=declaration
void insertLast(List* L, int x) {
	if (L != NULL) {
		while (*L != NULL && (*L)->data != x) L = &((*L)->next);

		if (*L == NULL) {
			nodetype* newNode = (nodetype*)malloc(sizeof(nodetype));

			if (newNode != NULL) {
				newNode->data = x;
				newNode->next = NULL;

				*L = newNode;
			}
		}
	}
}
```

**Use The Function**

```c title=main
#include <stdio.h>
#include <stdlib.h>

typedef struct node {
	int data;
	struct node *next;
} nodetype, *List;

void printList(List);

// Function Header
void insertLast(List*, int);

int main(void) {
	// Populate the list and define the element
	nodetype a = { data: 3, next: NULL };
	nodetype b = { data: 7, next: &a };
	nodetype c = { data: 1, next: &b };
	
	List L = &c;
	int elem = 2;
	
	printList(L);
	// Output: 1 7 3
	
	// Call the insertLast function
	insertLast(&L, elem);
	
	printList(L);
	// Output: 1 7 3 2
}

void printList(List L) {
	while (L != NULL) {
		printf("%d ", L->data);
		L = L->next;
	}
	
	printf("\n");
}

// * Function Definition
void insertLast(List* L, int x) {
	// Prevent NULL pointers
	if (L != NULL) {
		// Traverse through the linked list until it
		// reaches the last node, and the new data
		// must not be in the linked list
		while (*L != NULL && (*L)->data != x) L = &((*L)->next);
		
		// Check if L is the last node
		if (*L == NULL) {
			nodetype* newNode = (nodetype*)malloc(sizeof(nodetype));

			// Check if the allocation was a success
			if (newNode != NULL) {
				newNode->data = x;
				newNode->next = NULL;
				
				*L = newNode;
			}
		}
	}
}
```
