---
published: true
layout: post
title: (Bash) `cp`, `mv` with wildcard
---

1.  Use `find -name <NAME_TO_CAPTURE>` to capture filenames to copy or move,
    then dispatch those files to `cp` or `mv` using `-exec`
    - E.g. `find /home/admin -name "*.txt" -exec mv '{}' /home/admin/txtfiles/ \;`
    - Wildcard string (e.g. `"*.txt"`) must be enclosed by quotes
    - `{}` denotes each of the captured filenames
    - `\;` at the end is semi-colon escaped to denote end of command for `-exec`


2.  Another approach using `xargs`
    - E.g. `ls -1 *.txt | xargs -I{} mv /home/admin/{} /home/admin/txtfiles/{}`
    - `ls -1` prints `ls` output one-file-per-line
    - `-I{}` makes `{}` the placeholder for standard input
      (implies `-x -L 1` where `-L 1` makes `xargs` consider at most 1 line per command)


References:
- <https://stackoverflow.com/a/54635203>
- <https://stackoverflow.com/a/59248735>
