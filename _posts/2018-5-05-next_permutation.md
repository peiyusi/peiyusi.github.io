---
layout: post
title: Writing next_permutation function
date: 2018-5-5
author: 42
tags: C++
---

We can order different permutations in a specific rule, in C++ we can use the [next_permutation][1] function, like this 

```cpp
#include <iostream>     // std::cout
#include <algorithm>    // std::next_permutation, std::sort

int main () {
  int myints[] = {1,2,3};

  std::sort (myints,myints+3);

  std::cout << "The 3! possible permutations with 3 elements:\n";
  do {
    std::cout << myints[0] << ' ' << myints[1] << ' ' << myints[2] << '\n';
  } while ( std::next_permutation(myints,myints+3) );

  std::cout << "After loop: " << myints[0] << ' ' << myints[1] << ' ' << myints[2] << '\n';

  return 0;
}
```

Output:

```cpp
The 3! possible permutations with 3 elements:
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1
After loop: 1 2 3 
```

Algorithm:

* Finding two near-by elements i and ii from the end(i < ii), then find iii (iii > i), swap i and iii.
* Reverse elements behind ii.

 

My own version: 

```c
void mynext_permutation(int N)
{
    int x1, x2; 
  
    for (int i = N -1; i > 0; i--) {
        if (a[i] > a[i-1]) {
            x1 = i-1;
            x2 = i;
            break;
        }   
    }   
    for (int i = N-1; i > 0; i--) {
        if (a[i] > a[x1]) {
            swap(a[i], a[x1]);
            reverse(a+x2, a+N); 
            break;
        }   
    }   
}

```











[1]: http://www.cplusplus.com/reference/algorithm/next_permutation/