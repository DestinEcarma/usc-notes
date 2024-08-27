---
creation date: 2024-08-27T22:11:55
tags:
  - DSA
---

# Stack

A **Stack** is a linear data structure in *Data Structures and Algorithms (DSA)* that follows the **"Last-In-First-Out" (LIFO)** principle. This means that ==the last element added to the stack will be the first one to be removed==. Stacks are widely used in various scenarios such as expression evaluation, function call management, and undo mechanisms in text editors.

![[Stack.excalidraw|100%]]

Stacks are an essential data structure that provides an efficient way to manage data with a LIFO access pattern. With $O(1)$ time complexity for both push and pop operations when implemented with arrays or linked lists, stacks are widely used in algorithms and applications where reverse order processing is required.

## What is Stack Data Structure?

> A stack is a linear data structure that follows the **Last-In-First-Out (LIFO)** principle. It behaves like a stack of plates, where the last plate added is the first one to be removed.
> 
> **Think of it this way:**
> 
> - Pushing an element onto the stack is like adding a new plate on top.
> - Popping an element removes the top plate from the stack.
> 
> -- <cite>GeeksforGeeks, n.d.</cite>

## Basic Concepts:

- `Push`: The operation of adding an element to the top of the stack.
- `Pop`: The operation of removing the top element from the stack.
- `Top/Peek`: The current element at the top of the stack.
- `IsEmpty`: A check to see if the stack is empty.
- `IsFull`: A check to see if the stack is full (in the case of a bounded stack).

## Types of Stacks

- **Simple Stack:** A standard stack where elements are pushed onto and popped from the top of the stack.
- **Bounded Stack:** A stack with a fixed size. Once the stack is full, no more elements can be pushed onto it.
- **Dynamic Stack:** A stack where the size can grow dynamically as needed, often implemented using linked lists or dynamically resizing arrays.

## References

1. GeeksforGeeks. (n.d.). Stack Data Structure. Retrieved August 27, 2024, from https://www.geeksforgeeks.org/stack-data-structure
