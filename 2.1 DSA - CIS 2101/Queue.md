---
creation date: 2024-08-27T20:09:43
tags:
  - DSA
---

# Queue

A **Queue** is a linear data structure in *Data Structures and Algorithms (DSA)* that follows the **"First-In-First-Out" (FIFO)** principle. This means that the first element added to the queue will be the first one to be removed. Queues are used in various scenarios like scheduling tasks, managing resources in computer systems, and in *breadth-first search (BFS)* algorithms.

![[Queue.excalidraw|100%]]

Queues are a fundamental data structure in computer science, used whenever it's necessary to process elements in the order they were added. ==They provide efficient $O(1)$ time complexity for both enqueue and dequeue== operations when implemented with linked lists or circular arrays.

## What is Queue in Data Structures?

> A queue is a linear data structure that follows the **First-In-First-Out (FIFO)** principle. It operates like a line where elements are added at one end (rear) and removed from the other end (front).
> 
> -- <cite>GeeksforGeeks, n.d.</cite>

## Basic Concepts:

- `Enqueue`: The operation of adding an element to the end of the queue.
- `Dequeue`: The operation of removing an element from the front of the queue.
- `Peek/Top`: Returns the element at the front of the queue without removing it.
- `IsEmpty`: A check to see if the queue has any elements.
- `IsFull`: A check to see if the queue has reached its maximum capacity (in the case of a bounded queue).

## Types of Queues

1. **Simple Queue:** A basic queue that follows the FIFO principle.
2. **Circular Queue:** A queue that uses a circular array to store elements, allowing for efficient memory usage.
3. **Priority Queue:** A queue where elements are assigned a priority, and the element with the highest priority is removed first.
4. **Double-ended Queue (Deque):** A queue that allows insertion and deletion of elements from both ends.

## References

1. GeeksforGeeks. (n.d.). Queue Data Structure. Retrieved August 27, 2024, from https://www.geeksforgeeks.org/queue-data-structure
