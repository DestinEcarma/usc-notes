---
creation date: 2024-08-21T16:10:15
tags:
  - DSA
external links:
  - https://github.com/DestinEcarma/learning-c/tree/main/DSA/activity-3
---

# Activity 3

Write the code and the function that will return the middle element of the given [[Linked List|linked list]]. **Return a dummy value of a list if empty.**

Condition:

- 1 traversal only
- 1 return only
- Assume elements are positive integers.

```c title=datatype
typedef struct node {
	int data;
	struct node* next;
} *List;
```

## Answer

**Function Header**

```c title=header
int getMiddleElement(List);
```

**Function Declaration**

```c title=declaration
int getMiddleElement(List L) {
	int result = -1;

	if (L != NULL) {
		List slow = L;
		List fast = L;

		while (fast != NULL && fast->next != NULL) {
			slow = slow->next;
			fast = fast->next->next;
		}

		result = slow->data;
	}

	return result;
}
```
