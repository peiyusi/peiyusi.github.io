---
layout: post
title: 'Quicksort'
date: 2018-5-13
author: 42
tags: Algorithm
---

[Quicksort][1] is a common sorting algorithm, and the key process in quicksort is *partition*.

Target of partitions is, give an array  and an element x of array as pivot, put x at its correct position after sorted(put all smaller elements before it and all greater elements after it).

Picking the pivot is another important thing that we need to consider, because in the worst situation the time complexity will be O(N^2). One of the good ways to pick pivot is to choose the mediation of A[low], A[high] and A[(low+high) / 2].

Another problem is  when the array's size is small, the recursive process will be really slow, even slower than [Simple Selection Sort][2], so we can judge the size of choose the better sorting function before the recursive.

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





