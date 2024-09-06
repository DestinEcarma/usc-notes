---
creation date: 2024-09-06T23:04:18
tags:
  - DSA
---

# Activity 14

Create a function `displayBitPattern`, that should work for no matter what size. No array should be used and recursion is not allowed. Group the bits in groups of 4, separated by a space.

## Answer

```c title=implementation
void displayBitPattern(void* value, int size) {
	unsigned char* bytes = (unsigned char*) value;

	for (int i = size - 1; i >= 0 && size > 1; i--) {
		int j = 7;

		while (j >= 0) {
			if ((bytes[i] >> j & 1) == 1) {
				i = -1;
			}

			j--;
		}

		if (j < 0 && i >= 0) {
			size--;
		}
	}

	for (int i = size - 1; i >= 0; i--) {
		for (int j = 7; j >= 0; j--) {
			printf("%d", bytes[i] >> j & 1);

			if (j == 4) {
				printf(" ");
			}
		}

		printf(" ");
	}

	printf("\n");
}
```
