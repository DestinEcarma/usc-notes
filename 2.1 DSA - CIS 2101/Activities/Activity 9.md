---
creation date: 2024-08-27T22:10:13
tags:
  - DSA
external links:
  - https://github.com/DestinEcarma/learning-c/tree/main/DSA/activity-9
---

# Activity 9

Create a [[Stack|stack]] [[Abstract Data Type|ADT]] list of operations and implement the following operations:

1. `initialize`: Initialize the stack.
2. `push`: Add an element to the top of the stack.
3. `pop`: Remove an element from the top of the stack.
4. `top`: return the top element of the stack.
5. `isEmpty`: Check if the stack is empty.
6. `isFull`: Check if the stack is full.

Implement the stack using an [[Array Implementation|array]] and [[Linked List|linked list]].

## Answer

**Array**

```c title=datatype
#define MAX 10

typedef struct {
	int elems[MAX];
	int top;
} Stack;
```

```c title=implementation
void initialize(Stack* stack) {
	stack->top = -1;
}

void push(Stack* stack, int data) {
	if (isFull(stack) == false) {
		stack->elems[++stack->top] = data;
	}
}

void pop(Stack* stack) {
	if (isEmpty(stack) == false) {
		stack->top--;
	}
}

int top(Stack* stack) {
	int result = -1;

	if (isEmpty(stack) == false) {
		result = stack->elems[stack->top];
	}

	return result;
}

bool isEmpty(Stack* stack) {
	return stack->top == -1;
}

bool isFull(Stack* stack) {
	return stack->top == MAX - 1;
}
```

**Linked List**

```c title=datatype
typedef struct node {
	int data;
	struct node* next;
} Node, *Stack;
```

```c title=implementation
void initialize(Stack* stack) {
	*stack = NULL;
}

void push(Stack* stack, int data) {
	Node* newNode = (Node*)malloc(sizeof(Node));

	if (newNode != NULL) {
		newNode->data = data;
		newNode->next = *stack;
		*stack = newNode;
	}
}

void pop(Stack* stack, int data) {
	if (isEmpty(stack) == false) {
		Node* temp = *stack;
		*stack = temp->next;
	    free(temp);
	}
}

int top(Stack* stack) {
	int result = -1;

	if (isEmpty(stack) == false) {
		result = (*stack)->data;
	}

	return result;
}

bool isEmpty(Stack* stack) {
	return *stack == NULL;
}

bool isFull(Stack* stack) {
	return false;
}
```
