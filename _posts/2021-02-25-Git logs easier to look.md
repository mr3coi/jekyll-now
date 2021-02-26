---
published: true
layout: post
title: (Git) Make log easier to look into
---

1.  Use `git log --all --decorate --oneline --graph` to make log prettier and more concise
    - `--graph`: Show the graph of different branches
    - Can even run the following to use a shorter alias instead (`git adog`):
      `git config [--global] alias.adog 'log --all --decorate --oneline --graph'`

2.  Limit the number of commits shown: `git log -N`
    - `N` determines the number of the most recent commits to be shown
    - Can use in conjunction with `git adog`: e.g. `git adog -10`


Reference:
- <https://stackoverflow.com/a/10347287>
