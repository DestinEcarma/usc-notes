---
creation date: 2024-08-27T20:37:12
tags:
  - DSA
links:
  - "[[Array Implementation]]"
  - "[[Queues]]"
---

# Activity 8

Create a queue using an array. Implement the following operations:

1. `initQueue`: Initialize the queue.
2. `enqueue`: Add an element to the end of the queue.
3. `dequeue`: Remove an element from the front of the queue.

```c title=datatype
#define MAX 10

typedef struct {
  int elems[MAX];
  int front;
  int rear;
} Queue;
```

## Answer

```c title=initQueue
void initQueue(Queue* queue) {
  queue->front = 1;
  queue->rear = 0;
}
```

```c title=enqueue
void enqueue(Queue* queue) {
	if (queue->front != (queue->rear + 2) % MAX) {
	    queue->rear = (queue->rear + 1) % MAX;
	    queue->elems[queue->rear] = data;	
	}
}
```

```c  title=dequeue
void dequeue(Queue* queue) {
  if (queue->front != (queue->rear + 1) % MAX) {
      queue->front = (queue->front + 1) % MAX;
  }
}
```
