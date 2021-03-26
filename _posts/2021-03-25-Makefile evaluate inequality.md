---
published: true
layout: post
title: (Makefile) Evaluate inequality
---

1.  Makefile syntax alone only supports equal / not equal

2.  Hence combine with shell command. E.g. to see if `VAL_A > VAL_B`:
    ```
    ifeq ($(shell test $(VAL_A) -gt $(VAL_B); echo $$?), 0)
      # ...DO SOMETHING...
    endif
    ```
    - `$?` designates the return value of the last shell cmd (in this case `test ...`)
    - `$?` has an extra $ sign to escape the $ for evaluation by shell
    - `test` returns 0 if true, else 1
    - `VAL_A`, `VAL_B` can instead be constant values


References:
- <https://stackoverflow.com/a/28354572>
- <https://stackoverflow.com/questions/6834487/what-is-the-dollar-question-mark-variable-in-shell-scripting>
