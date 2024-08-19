---
creation date: 2024-08-17T22:30:57
---

# Trailing Pointers

Trailing pointers involve using two pointers as you traverse the linked list. ==One pointer `curr` is used to reference the current node, and the other `prev` trails behind==, pointing to the previous node. This technique is particularly useful for operations like deletion or insertion after a specific node.

The `prev` pointer follows the `curr` pointer through the list, always pointing to the node before the current one. This allows you to easily modify the list by updating the `next` pointer of the `prev` node.

```c title=example.c
void deleteNode(Node** headRef, int key) {
    Node* curr = *headRef;
    Node* prev = NULL;

    while (curr != NULL && curr->data != key) {
        prev = curr;
        curr = curr->next;
    }

	if (curr != NULL) {
		if (prev == NULL) {
	        *headRef = curr->next;
	    } else {
	        prev->next = curr->next;
	    }

	    free(curr);
	}
}
```
