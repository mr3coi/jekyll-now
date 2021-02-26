---
published: true
layout: post
title: (Git) Only cherry-pick a subset of files from a commit
---

1.  Use `git cherry-pick -n <COMMIT_SHA1>` to load all changes in the commit but only as staged
    (i.e. not committed to the current branch)
    - `-n`: `--no-commit`

2.  Unstage all the **unnecessary** file changes
    - If only very few files are desired, then run `git reset HEAD` to unstage all changes,
      then re-stage only the desired files

3.  Commit the staged files


Reference:
- <https://stackoverflow.com/questions/5717026/how-to-git-cherry-pick-only-changes-to-certain-files>
