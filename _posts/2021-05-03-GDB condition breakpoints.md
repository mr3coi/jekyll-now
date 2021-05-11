---
published: true
layout: post
title: (gdb) Condition breakpoints
---

1.  Define breakpoint with condition: `b[reak] <BREAK_LOC> if <CONDITION>`
    - Here `<CONDITION>` can use the variables and functions that are locally visible
      within the scope of the breaking line


2.  Specify condition to existing breakpoint: `condition <BREAKPOINT_NUM> (<CONDITION>)`
    - Note the presence of parentheses in place of the missing `if`
    - To unconditionally break on the breakpoint (i.e. remove condition): `condition <BREAKPOINT_NUM>`


3.  Ignore a breakpoint for `N` times: `ignore <BREAKPOINT_NUM> N`
    - If the breakpoint is conditioned, the condition is not checked until the ignore count `N` is used up


References:
- <https://sourceware.org/gdb/onlinedocs/gdb/Conditions.html>
- <https://sourceware.org/gdb/onlinedocs/gdb/Conditions.html>
