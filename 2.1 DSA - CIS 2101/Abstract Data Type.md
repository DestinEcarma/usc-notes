---
creation date: 2024-08-28T18:14:02
tags:
  - DSA
aliases:
  - ADT
---

# Abstract Data Type

An **Abstract Data Type (ADT)** is a theoretical concept in computer science that defines a data structure purely by its behavior *(operations and properties)*, rather than by its implementation. ADTs focus on what the data structure does, not how it is done. This abstraction allows for the implementation details to change without affecting the way the data type is used by other parts of a program.

> Abstract Data type (ADT) is a type (or class) for objects whose behavior is defined by a set of values and a set of operations. The definition of ADT only mentions what operations are to be performed but not how these operations will be implemented. It does not specify how data will be organized in memory and what algorithms will be used for implementing the operations. It is called “abstract” because it gives an implementation-independent view
> 
> -- <cite>GeeksforGeeks, n.d.</cite>

## Key Characteristics of ADTs

- **Encapsulation**: ADTs encapsulate data and operations into a single unit, providing a clean interface for interacting with the data.
- **Operations**: ADTs define a set of operations that can be performed on the data structure, such as insertion, deletion, and traversal.
- **Data and State**: ADTs define the data that is stored and the state of the data structure at any given time.

## Examples of ADTs

Some common examples of Abstract Data Types include:

- **List**: A data structure that stores a collection of elements in a specific order.
- **[[Stack]]**: A data structure that follows the **Last-In-First-Out (LIFO)** principle.
- **[[Queues]]**: A data structure that follows the **First-In-First-Out (FIFO)** principle.

## References

1. GeeksforGeeks. (n.d.). Abstract Data Types. Retrieved August 28, 2024, from https://www.geeksforgeeks.org/abstract-data-types
