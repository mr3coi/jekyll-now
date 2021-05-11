---
published: true
layout: post
title: (gdb) Print long string without truncation
---

Run `set print elements 0`.
- When the last number is a positive integer, it denotes the number of elements in an array (in this case,
  a char array since our target is a string) that should be printed without truncation.
- `0` represents no limit; every element will be printed out.


References:
- <https://stackoverflow.com/questions/233328/how-do-i-print-the-full-value-of-a-long-string-in-gdb>
