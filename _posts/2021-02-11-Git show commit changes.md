---
published: true
layout: post
title: (Git) Show commit changes/commit differences
---

1.  Show changes made in a single commit

    ```
    git show <sha1-commit-hash>
    ```
    Adding `--name-only` will only show the commit title & comment of the commit.
   
2.  Show differences between two comits

    ```
    git diff <REFERENCE sha1-commit-hash>~ <TARGET sha1-commit-hash>
    ```
    where the tilde(`~`) is necessary in the above syntax.
    The above command highlights the changes in TARGET commit as compared to REFERENCE commit.
    Flipping the order would change additions to deletions and vice versa.


Reference:
- <https://stackoverflow.com/questions/17563726/how-to-see-the-changes-in-a-git-commit>
