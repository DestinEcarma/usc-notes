---
creation date: 2024-08-24T23:25:52
tags:
  - DSA
links:
  - "[[Array Implementation]]"
---

# Activity 6

Write a program that satisfies the following conditions:

1. The program will allow users to perform the following List operations:

	- `insert(x, p, L)` - insert element `x` at position `p` in the list `L`.
	- `delete(p, L)` - delete the element at position `p` in the list `L` if `p` is a valid position.
	- `p = locate(x, L)` - returns the position of `p` of element `x` in the list `L`. Return a dummy position if `x` is not in the list.
	- `x = retrieve(p, L)` - returns the element `x` at position `p` of the list `L`. Return a dummy element value if `p` is not valid.
	- `makenull(L)` - makes the list `L` empty.
	- `printList(L)` - lists the elements of the list `L`.

2. The elements of the list are student records. The initial entries of the list will come from the given file.
3. Program should be modular, the main function will be as short as possible and will contain variable declarations and as much as possible function calls **ONLY**.

## Answer

```c title=datatypes
typedef char String[50];
typedef int Position;

typedef struct {
	String fName;
	String lName;
	char mInitial;
} Name;

typedef struct {
	int studentId;
	int year;
	String course;
	Name name;
} Student;

typedef struct {
	Student *students;
	int count;
	int arrSize;
} List, *ListPtr;
```

```c title=declarations
void insert(Student elem, Position pos, ListPtr list) {
	if (pos <= list->count) {
		if (list->count == list->arrSize) {
			Student* newArr = (Student*)realloc(
				list->students,
				sizeof(Student) * (list->arrSize * 2)
			);

			if (newArr != NULL) {
				list->students = newArr;
				list->arrSize *= 2;
			}
		}

		if (list->count < list->arrSize) {
			memmove(
				list->students + pos + 1,
				list->students + pos,
				sizeof(Student) * (list->count - pos)
			);

			list->students[pos] = elem;
			list->count++;
		}
	}
}

void delete(Position pos, ListPtr list) {
	if (pos < list->count) {
		memmove(
			list->students + pos,
			list->students + pos + 1,
			sizeof(Student) * (list->count - pos - 1)
		);

		list->count--;

		if (list->arrSize != 0 && list->count == (list->arrSize / 2)) {
			Student* newArr = (Student*)realloc(
				list->students,
				sizeof(Student) * (list->arrSize / 2)
			);
			
			if (newArr != NULL) {
				list->students = newArr;
				list->arrSize /= 2;
			}
		}
	}
}

Position locate(Student elem, ListPtr list) {
	Position pos = -1;

	for (int i = 0; i < list->count && pos == -1; i++) {
		if (list->students[i].studentId == elem.studentId) {
			pos = i;
		}
	}

	return pos;
}

Student retrieve(Position pos, ListPtr list) {
	Student result = { studentId: -1 };

	if (pos < list->count) {
		result = list->students[pos];
	}

	return result;
}

void makenull(ListPtr list) {
	list->count = 0;
}

void printList(ListPtr list) {
	for (int i = 0; i < list->count; i++) {
		Student* elem = list->students + i;

		printf(
			"[%d]: ID: %d, Name: %s %c. %s, Course: %s, Year: %s\n",
			i + 1,
			elem->studentId
			elem->name.fName,
			elem->name.mInitial,
			elem->name.lName,
			elem->course,
			elem->year
		);
	}
}
```

```c title=main
void initialize(ListPtr, int);

int main(void) {
	List studentList;

	initialize(&list, 10);

	insert((Student) {
		.name = { "Destin", "Ecarma", 'R' },
		.course = "BSCS",
		.studentId = 23100411,
		.year = 2
	}, 0, &list);

	printList(&list);

	return 0;
}

void initialize(ListPtr L, int arrSize) {
	L->students = (Student*)malloc(sizeof(Student) * arrSize);
	L->arrSize = arrSize;
	L->count = 0;
}
```
