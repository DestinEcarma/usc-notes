---
creation date: 2024-08-21T16:25:23
tags:
---

# Activity #4

Based on the definition of the array implementation of list write the code of the ff:

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

```c title=deletion
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
	if (list->count > 0) {
		for (int i = 0; i < list->count; i++) {
			if (list->elems[i] == elem) {
				memmove(
					list->elems + i,
					list->elems + i + 1,
					sizeof(int) * (list->count - i - 1)
				);

				i--;
				list->count--;
			}
		}
	}
}
```
