---
creation date: 2024-08-17T22:30:02
---

# Look-Ahead Technique

The look-ahead technique is ==used to access or modify the next node in the list while still processing the current node==. This is useful when you need to make decisions based on the next node's data or structure.

As you traverse the list, you keep an eye on the node following the current node. This allows you to make changes or decisions based on the properties of the next node.

```c title=example.c
void deleteAfter(Node* head, int key) {
	Node* curr = head;

	if (curr != NULL) {
		while (
			curr->data != key && \ // `\` is not needed on modern compilers
			curr->next != NULL
		) curr = curr->next;

		if (curr->next != NULL) {
		    Node* temp = curr->next;
			curr->next = temp->next;
			free(temp);
		}
	}
}
```
