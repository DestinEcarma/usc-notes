---
creation date: 2024-08-29T19:28:48
tags:
  - DSA
**external** links:
  - https://github.com/DestinEcarma/learning-c/tree/main/DSA/activity-10
---

# Activity 10

Create a [[Cursor Based Implementation|cursor based implementation]] of operations for a linked list. Implement the following operations:

1. `initList`: Initialize the linked list.
2. `allocSpace`: Allocate space for a new node.
3. `deallocSpace`: Deallocate space for a node.
4. `insertFirst`: Insert an element at the beginning of the list.
5. `insertLast`: Insert an element at the end of the list.
6. `insertSorted`: Insert an element in sorted order.
7.  `deleteElem`: Delete an element from the list.

```c  title=datatype
#define MAX 10

typedef int List;

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

```c title=implementatio
void initList(Cursor* cursor) {
	cursor->avail = MAX - 1;

	for (int i = 0; i < MAX; i++) {
		cursor->nodes[i].link = i - 1;
	}
}

int allocSpace(Cursor* cursor) {
	int result = cursor->avail;

	if (result != -1) {
		cursor->avail = cursor->nodes[result].link;
	}

	return result;
}

void deallocSpace(Cursor* cursor, int i) {
	if (i >= 0 && i < MAX) {
		cursor->nodes[i].link = cursor->avail;
	    cursor->avail = i;
	}
}

void insertFirst(Cursor* cursor, List* head, int data) {
	int i = allocSpace(cursor);

	if (i != -1) {
		Node* node = cursor->nodes + i;

	    node->data = data;
	    node->link = *head;

	    *head = i;
	}
}

void insertLast(Cursor* cursor, List* head, int data) {
	int i = allocSpace(cursor);

	if (i != -1) {
		Node* node = cursor->nodes + i;

		while (*head != -1) {
			head = &cursor->nodes[*head].link;
		}

		node->data = data;
		node->link = -1;
		*head = i;
	}
}

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

void deleteData(Cursor* cursor, List* head, int data) {
	if (*head != -1) {
		Node* curr = cursor->nodes + *head;

		while (curr->link != -1 && curr->data != data) {
			head = &curr->link;
			curr = cursor->nodes + *head;
		}

		if (curr->data == data) {
			int temp = *head;
			*head = curr->link;
			deallocSpace(cursor, temp);
		}
	}
}
```
