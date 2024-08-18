# Pointer To Pointer To Node

A pointer to a pointer to a node `Node**` is a technique used to manipulate linked lists, particularly when dealing with operations like inserting or deleting nodes.

Normally, a pointer to a node `Node*` directly refers to a specific node in the list. However, a pointer to a pointer `Node**` ==allows you to modify the actual pointer that points to a node==. This is particularly useful when you need to change the head of the list or when you want to change the next pointer of a node without needing to handle special cases separately.

```c title=example.c
void insertAtHead(Node** headRef, int newData) {
	Node* newNode = (Node*)malloc(sizeof(Node));
	newNode->data = newData;
	newNode->next = NULL;

	*headRef = newNode;
}
```

---

**Date:** 2024 August, 17 10:42 PM<br>