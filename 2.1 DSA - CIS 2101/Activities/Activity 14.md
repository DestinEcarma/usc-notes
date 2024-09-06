---
creation date: 2024-09-06T23:04:18
tags:
  - DSA
---

# Activity 14

Create a function `displayBitPattern`, that should work for no matter what size. No array should be used and recursion is not allowed. Group the bits in groups of 4, separated by a space.

## Answer

```c title=implementation
void displayBitPattern(int value) {
	int byte = sizeof(value);
	int size = byte * 8;

	for (int i = size - 1; i >= 0 && (value >> i & 1) == 0; i--) {
	  if (i % 8 == 0) {
	    byte--;
	  }
	}
 
	for (int i = byte * 8 - 1; i >= 0; i--) {
		printf("%d", value >> i & 1);

		if (i % 4 == 0) {
			printf(" ");
		}
	}
}
```
