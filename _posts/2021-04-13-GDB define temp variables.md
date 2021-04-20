---
published: true
layout: post
title: (gdb) Define temporary variables
---

- Defining temporary variables may help make commands shorter and easier to read.

- In gdb, run `set $<NEWVAR> = <CMD>` to define a new variable `<NEWVAR>`
    - E.g. If under the current context there is a vector named `items`,
      we can create a variable `firstItem` to point to its first element as follows:
      ```
      set $firstItem = *(items._M_impl._M_start+0)
      ```
    - The $ sign is crucial; without the $ sign, gdb will look for a variable with the given name
      from within the program being run.


References:
- <https://sourceware.org/gdb/onlinedocs/gdb/Convenience-Vars.html>
