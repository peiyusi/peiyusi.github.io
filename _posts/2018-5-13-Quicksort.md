---
layout: post
title: 'Quicksort'
date: 2018-5-13
author: 42
tags: Data-Structures
---

The partition process is vital, the idea can be used for many problems, for example, given an array, move all the odd number in front of the even number. Use two pointers start and end respectively, and swap the odd and even.

```c++
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int partition (int a[], int first, int last) {
    int pivot = a[last];
    int i = first - 1;
    for (int j = first; j <= last - 1; j++) {
        if (a[j] <= pivot) {
            i++;
            swap(&a[i], &a[j]);
        }
    }
    swap(&a[i + 1], &a[last]);

    return i + 1;
}

void quicksort(int a[], int first, int last) {
    if (first < last) {
        int pi = partition(a, first, last);
        quicksort(a, first, pi - 1);
        quicksort(a, pi + 1, last);
    }
}
```





[1]: https://en.wikipedia.org/wiki/Quicksort	"Quicksort"
[2]: https://en.wikipedia.org/wiki/Selection_sort	"Selection_sort"





