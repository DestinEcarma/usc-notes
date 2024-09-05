---
creation date: 2024-09-01T22:22:38
tags:
  - DSA
---

# Cursor Based Implementation

A cursor-based implementation refers to a technique where an array is used to simulate linked data structures like linked lists, avoiding the use of dynamic memory allocation (like `malloc()` in C). Instead of using pointers to reference other nodes, indices (or cursors) are used to traverse and manage the data structure. This method is particularly useful in environments where dynamic memory is not available or where memory allocation must be controlled tightly, such as embedded systems.

The key idea is that each node in the **Cursor** array simulates a node in a linked list, and the **link** field acts as the pointer by holding the index of the next node.

```c title=datatype
#define MAX 10

typedef struct {
    int data;
    int link;
} Node;

typedef struct {
	Node nodes[MAX];
	int avail;
} VirtualHeap;
```

In the above code, `Node` represents a node in the linked list, where `data` holds the actual data, and `link` holds the index of the next node. The `VirtualHeap` structure simulates the heap memory, and `avail` keeps track of the next available slot in the cursor array.

The `malloc` function is simulated by the `allocSpace` function, which returns the index of the next available slot in the cursor array.

```c title=allocSpace
int allocSpace(VirtualHeap* heap) {
	int avail = heap->avail;

	if (avail != -1) {
		heap->avail = heap->nodes[avail].link;
	}

	return avail;
}
```

The `free` function is simulated by the `deallocSpace` function, which deallocates the space by adding the index back to the available list.

```c title=deallocSpace
void deallocSpace(VirtualHeap* heap, int index) {
	if (index >= 0 && index < MAX) {
		heap->nodes[index].link = heap->avail;
		heap->avail = index;
	}
}
```
