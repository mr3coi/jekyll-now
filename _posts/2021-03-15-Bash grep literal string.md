---
published: true
layout: post
title: (Bash) Grep literal string w/o regex
---

Use `grep -F <TARGET>` to search w/o regex parsing.
E.g. `grep 7.2.1` also matches with `70201`, but `grep -F 7.2.1` doesn't.

NOTE: `grep -F` is equivalent to `fgrep` but directly calling `fgrep` is deprecated.


References:
- <https://stackoverflow.com/questions/14347722/how-to-grep-exact-literal-string-no-regex>
