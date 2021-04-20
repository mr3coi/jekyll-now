---
published: true
layout: post
title: (gdb) Delete a location in a breakpoint
---

1.  Basics: `d[el[ete]] <BREAKPOINT_INDEX>`

2.  Situation where a breakpoint has multiple locations:
    e.g. given multiple overloads of function `foo`, break on `foo` (i.e. `b foo`)
    - A representative index (say `x`) is assigned for the breakpoint
    - Each specific overload of `foo` occurs in a different location,
      hence a sub-index `x.y` is assigned (`y=1,2,...`)

3.  Deleting a single location of occurrence of the breakpoint is not allowed (i.e. `d x.y` doesn't work).
    - Since there is still only a single breakpoint, only multiple locations of it
    - Instead, each location can be independently disabled: `disable x.y`

4.  Multiple locations in a breakpoint can be disabled simultaneously by specifying a range in their indices:
    `disable x.y-z` disables `x.y`, `x.(y+1)`, ..., `x.z`

5.  To disable/delete ALL breakpoints: run `disable` or `delete` without arguments


References:
- <https://stackoverflow.com/questions/54417220/how-to-delete-a-breakpoint-from-multiple-breakpoint-list-in-gdb>
- <https://stackoverflow.com/questions/59599200/clear-all-breakpoints-in-gdb>
