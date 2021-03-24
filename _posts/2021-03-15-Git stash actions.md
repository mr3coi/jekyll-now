---
published: true
layout: post
title: (Git) Detailed stash commands
---

1.  Stash all unstaged updated files with customized message: `git stash save <STASH_MESSAGE>`


2.  Stash only specific subset of updated files: `git stash push <FILES_LIST>`
    - Additionally provide customized message: `git stash push -m <STASH_MESSAGE> <FILES_LIST>`


References:
- <https://stackoverflow.com/questions/5506339/how-can-i-git-stash-a-specific-file>
- <https://stackoverflow.com/a/44681952>
