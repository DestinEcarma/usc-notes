---
creation date: 2024-09-03T17:54:34
tags:
  - DSA
---

# Activity 11

Create a [[Cursor Based Implementation|cursor based implementation]] of operations for a linked list. Implement the following operations:

1. `insertSorted`: Insert an element in sorted order.
2. `isEqualList`: Check if two lists are equal.
	- The list is sorted
	- The list is unsorted

```c title=datatype
#define MAX 10

typedef int List;

typedef enum {
	FALSE,
	TRUE
} boolean;

typedef struct {
	int data;
	int link;
} Node;

typedef struct {
	Node nodes[MAX];
	List avail;
} Cursor;
```

## Answer

```c title=implementation
void insertSorted(Cursor* cursor, List* head, int data) {
	int i = allocSpace(cursor);

	if (i != -1) {
		Node* node = cursor->nodes + i;

		while (*head != -1 && cursor->nodes[*head].data < data) {
			head = &cursor->nodes[*head].link;
		}

		node->data = data;
		node->link = *head;
		*head = i;
	}
}

boolean isEqualListOrderedTest(Cursor* cursor, List A, List B) {
	while (
		A != -1 && B != -1 &&
		&cursor->nodes[A].data != &curosr->nodes[B].data
	) {
		A = &cursor->nodes[A].link;
		B = &cursor->nodes[B].link;
	}

	return (A == -1 && B == -1) TRUE : FALSE;
}

boolean isEqualListUnorderedTest(Cursor* cursor, List A, List B) {
	boolean result = TRUE;

	while (result == TRUE && A != -1) {
		List trav = B;

		while (
			trav != -1 && trav &&
			cursor->nodes[A].data != cursor->nodes[trav].data
		) {
			trav = cursor->nodes[trav].link;
		}

		if (trav == -1) {
			result = FALSE;
		}

		A = cursor->nodes[A].link;
	}

	return result;
}
```
