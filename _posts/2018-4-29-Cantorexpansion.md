---
layout: post
title: 'Cantor expansion'
date: 2018-4-25
author: 42
tags: Algorithm
---

Let's talk about *Full Permutation*. Select m members from a set of n (m <= n) into some sequence or order, *Full Permutation* is when m = n.

For a *Full Permutation* of n, we have totally n! orders, how to we know the specific order? Take an example:

```c
For 9 permutation, where is 842697513?
Look at 8, the first number, the permutations of 1 to 7  as the first number are smaller than it, so we have totally (7 * 8!) permutations.
Than 4, the second number, the permutations of 1 to 3 as the second number are smalle than it,  
```

