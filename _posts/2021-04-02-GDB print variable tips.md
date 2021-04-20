---
published: true
layout: post
title: (gdb) Tips on printing variables
---

1.  Printing type of variable: `ptype <VARIABLE_SYMBOL>`
    - For class objects, prints the signature of the whole class

2.  Printing a vector: `p[rint] <VECTOR>`

3.  Printing an element in a vector:
    - Often `operator[]` or `at()` method don't work in gdb
    - Instead, use `<VECTOR>._M_impl._M_start+<INDEX>`
    - This will return the pointer to the target element in the underlying array,
      so dereferencing the pointer would give the element


References:
- <https://stackoverflow.com/a/30921053>
- <https://sourceware.org/gdb/current/onlinedocs/gdb/Symbols.html>
- <https://stackoverflow.com/a/2123260>
- <https://stackoverflow.com/a/47153592>
