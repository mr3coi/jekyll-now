---
published: true
layout: post
title: (gdb) Basic usage instructions
---

1.  Executables have to be first compiled with `-g` flag so that extra information
    such as source code & line number are embedded into the executables


2.  To execute gdb: `gdb <EXECUTABLE_NAME>`
    - To debug an executable which requires cmdline arguments:
      `gdb --args <EXECUTABLE_NAME> <ARGUMENTS>` or specify args within gdb


3.  Flow control commands (square brackets can be abbreviated):
    - `r[un]`: Run the executable
      - To specify args for execution: `r <ARGS>`
    - `b[reak] <TARGET>`: Create a breakpoint at location `<TARGET>`
      where `<TARGET>` can be one of the following:
      - `function_name`
        - Supports class name, scope resolution operator
        - In case of overloaded function, can uniquely identify by providing parameter types
        - If fully namespace-qualified, a `<TAB>` would prompt gdb to do tab-completion
      - `file_name:function_name`
      - `line_number`
      - `file_name:line_number`
      - `+offset`, `-offset`: position from currently selected stack frame
      - No argument: break at next instruction in the currently selected stack frame
    - `rbreak <TARGET>`: To enable wildcards and regex in breakpoint matching
    - `s[tep]`: Continue to the next instruction
    - `n[ext]`: Continue to the next stack frame (after completing the current stack frame)
    - `c[ontinue]`: Continue to the next breakpoint or the end of the program
    - `d[el[ete]] <BREAKPOINT_ID>`: Deletes the breakpoint with ID `<BREAKPOINT_ID>`
      - Run w/o any argument to delete all breakpoints at once
    - `disable <BREAKPOINT_ID>`: Disables the breakpoint with ID `<BREAKPOINT_ID>`
      - Run w/o any argument to disable all breakpoints at once
    - `q[uit]`: Quits gdb
      - Can be called during run


4.  Observation commands
    - `info <ITEM>`: Shows a list of `<ITEM>` which can be one of the following:
      - `b[reakpoints]`: List all breakpoints (ID, line info, etc.)
      - `sharedlibrary`: List all dynamically-linked libraries as of now
      - `f[rame]`: Describes the current stack frame
      - `r[egisters]`: List of registers and the values they are currently storing
    - `p[rint] <VARIABLE>`: Prints the value of `<VARIABLE>`
      - Many variants here; TODO: fill in
      - Use `ptype` instead to print a type (works for recent enough gdb)
    - `f[rame]`: Shows the current frame as well as instruction as a line in the source code
    - `l[ist]`: Shows the current source code line + a few lines above & below
      - Continuously running `list` prints out the subsequent lines
        until the end of the current source file
    - `b[ack]t[race]`: Shows the stack trace to the current stack frame
      - `where` is an exact synonym
    - `disas <FUNCTION_NAME>`: Disassemble `<FUNCTION_NAME>` to see the underlying assembly code


5.  gdb & templates
    - Templates can be used to uniquely specify breakpoints
      - e.g. `b Foo<const char *>::Foo`
    - To break on all instances of class template `Foo`: `rbreak Foo<.*>`


6.  Misc.
    - Meaning of `<FUNCTION_NAME>@plt`: refer to reference (\*)


References:
- <https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_28.html>
- <https://stackoverflow.com/questions/59599200/clear-all-breakpoints-in-gdb>
- <https://stackoverflow.com/questions/39421971/in-gdb-whats-the-difference-between-where-bt-and-i-frame-commands>
- <https://stackoverflow.com/questions/14581837/gdb-how-to-print-the-current-line-or-find-the-current-line-number>
- <https://cets.seas.upenn.edu/answers/gcc.html>
- <https://stackoverflow.com/questions/35806129/c-gdb-breakpoint-for-member-functions>
- <https://stackoverflow.com/questions/33661179/debug-c-template-with-gdb?rq=1>
- <https://stackoverflow.com/questions/5469274/what-does-plt-mean-here> (\*)
