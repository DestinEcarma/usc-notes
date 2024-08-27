---
creation date: 2024-08-27T20:07:08
tags:
  - DSA
links:
  - "[[Linked List]]"
  - "[[Queues]]"
---

# Activity 7

Create a queue using a linked list. Implement the following operations:

1. `initQueue`: Initialize the queue.
2. `enqueue`: Add an element to the end of the queue.
3. `dequeue`: Remove an element from the front of the queue.

```c title=datatype
typedef struct node {
	int data;
	struct node* next;
} Node;

typedef struct {
	Node* front;
	Node* rear;
} Queue;
```

## Answer

```c title=initQueue
void initQueue(Queue* queue) {
	queue->front = NULL;
	queue->rear = NULL;
}
```

```c title=enqueue
void enqueue(Queue* queue, int data) {
	Node* newNode = (Node*)malloc(sizeof(Node));

	if (newNode != NULL) {
		newNode->data = data;
		newNode->next = NULL;

		if (queue->front == NULL) {
			queue->front = newNode;
		} else {
			queue->rear->next = newNode;
		}

		queue->rear = newNode;
	}
}
```

```c title=dequeue
void dequeue(Queue* queue) {
	if (queue->front != NULL) {
	    Node* temp = queue->front;
	    queue->front = temp->next;
	
	    if (queue->front == NULL) {
	      queue->rear = NULL;
	    }
	
	    free(temp);
	}
}
```
