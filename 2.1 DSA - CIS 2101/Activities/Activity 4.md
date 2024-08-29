---
creation date: 2024-08-21T16:25:23
tags:
  - DSA
---

# Activity 4

Based on the definition of the [[Array Implementation|array implementation]] of list write the code of the ff:

1. `initList()`
2. `insertLast()`
3. `insertLastUnique()`
4. `deleteElem()`
5. `deleteAllOccur()`
6.  `insertSorted()`

```c title=pre-defined
#define MAX 100

typedef struct {
	int elems[MAX]
	int count;
} List;
```

## Answer

**Function Header**

```c title=header
void initList(List*);

void insertLast(List*, int);
void insertLastUnique(List*, int);
void insertSorted(List*, int);

void deleteElem(List*, int);
void deleteAllOccur(List*, int);
```

**Function Declaration**

```c title=initialization
void initList(List* list) {
	list->count = 0;
}
```

```c title=insertion
void insertLast(List* list, int elem) {
	if (list->count < MAX) {
		list->elems[list->count++] = elem;
	}
}

void insertLastUnique(List* list, int elem) {
	if (list->count < MAX) {
		int i = 0;

		while (i < list->count && list->elems[i] != elem) {
			i++;
		}

		if (i == list->count) {
			list->elems[list->count++] = elem;	
		}
	}
}
```

```c title=insertion-loop-shift
void insertSorted(List* list, int elem) {
	if (list->count < MAX) {
		int i = 0;

		while (i < list->count && list->elems[i] < elem) {
			i++;
		}

		for (int j = list->count - 1; j >= i; j--) {
			list->elems[j + 1] = list->elems[j];
		}

		list->elems[i] = elem;
		list->count++;
	}
}
```

```c title=insertion-memmove
void insertSorted(List* list, int elem) {
	if (list->count < MAX) {
		int i = 0;

		while (i < list->count && list->elems[i] < elem) {
			i++;
		}

		memmove(
			list->elems + i + 1,
			list->elems + i,
			sizeof(int) * (list->count - i)
		);

		list->elems[i] = elem;
		list->count++;
	}
}
```

```c title=deletion-loop-shift
void deleteElem(List* list, int elem) {
	if (list->count > 0) {
		int i = 0;

		while (i < list->count && list->elems[i] != elem) {
			i++;
        }

		if (i < list->count) {
			list->count--;

			for (int j = i; j < list->count; j++) {
				list->elems[j] = list->elems[j + 1];
			}
		}
	}
}

void deleteAllOccur(List* list, int elem) {
	int i = 0;
	
	while (i < list->count) {
		if (list->elems[i] == elem) {
			list->count--;

			for (int j = i; j < list->count; j++) {
				list->elems[j] = list->elems[j + 1];
			}
		} else {
			i++;
		}
	}
}
```

```c title=deletion-memmove
void deleteElem(List* list, int elem) {
	if (list->count > 0) {
		int i = 0;

		while (i < list->count && list->elems[i] != elem) {
			i++;
        }

		if (i < list->count) {
			memmove(
				list->elems + i,
				list->elems + i + 1,
				sizeof(int) * (list->count - i - 1)
			);

			list->count--;
		}
	}
}

void deleteAllOccur(List* list, int elem) {
	int i = 0;
	
	while (i < list->count) {
		if (list->elems[i] == elem) {
			memmove(
				list->elems + i,
				list->elems + i + 1,
				sizeof(int) * (list->count - i - 1)
			);

			list->count--;
		} else {
			i++;
		}
	}
}
```
