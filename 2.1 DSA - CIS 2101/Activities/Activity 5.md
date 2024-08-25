---
creation date: 2024-08-24T23:05:47
tags:
  - DSA
links:
  - "[[Array Implementation]]"
---

# Activity 5

1. Write the appropriate definition of data type **LIST** and declaration of variable `L` using the following:

	- Version 2
	- Version 3
	- Version 4

2.  Write the code of function `Initialize()` for each of the above version.

## Answer

**Version 2**

```c title=version-2
#define MAX 10

typedef struct {
	int elems[MAX];
	int count;
} List, *ListPtr;

void Initialize(ListPtr* L) {
	*L = (ListPtr)malloc(sizeof(List));
	
	if (*L != NULL) {
		(*L)->count = 0;
	}
}

int main(void) {
	ListPtr L;

	Initlialize(&L);

	return 0;
}
```

**Version 3**

```c title=version-3
typedef struct {
	int *elemPtr;
	int count;
	int arrSize;
} List, *ListPtr;

void Initialize(ListPtr L, int arrSize) {
	L->elemPtr = (int*)malloc(sizeof(int) * arrSize);
	L->arrSize = arrSize;
	L->count = 0;
}

int main(void) {
	int arrSize = 10;
	List L;

	Initialize(&L, arrSize);

	return 0;
}
```

**Version 4**

```c title=version-4
typedef struct {
	int *elemPtr;
	int count;
	int arrSize;
} List, *ListPtr;

void Initialize(ListPtr* L, int arrSize) {
	*L = (ListPtr)malloc(sizeof(List));

	if (*L != NULL) {
		(*L)->elemPtr = (int*)malloc(sizeof(int) * arrSize);
		(*L)->arrSize = arrSize;
		(*L)->count = 0;
	}
}

int main(void) {
	int arrSize = 10;
	ListPtr L;

	Initialize(&L, arrSize);

	return 0;
}
```
