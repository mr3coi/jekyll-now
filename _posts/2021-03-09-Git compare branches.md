---
published: true
layout: post
title: (Git) Contrast two different branches
---

1.  Directly contrast target branch from reference branch

    ```
    git diff <REF_BRANCH_NAME>..<TARGET_BRANCH_NAME>
    ```
    - To only compare for a specific file:

      ```
      git diff <REF_BRANCH_NAME>..<TARGET_BRANCH_NAME> -- <FILE_NAME>
      ```
   

2.  Show all changes in target branch that are not in the reference branch
    (i.e. contrast target branch with the most recent common ancestor of the two branches)

    ```
    # NOTE that there are three dots in the midddle this time, not two
    git diff <REF_BRANCH_NAME>...<TARGET_BRANCH_NAME>
    ```
    - Likewise, to only compare for a specific file:

      ```
      git diff <REF_BRANCH_NAME>...<TARGET_BRANCH_NAME> -- <FILE_NAME>
      ```
    - The first approach is used much more often than this approach,
      since often there can be changes made by others to reference branch that
      one needs to take into account.


3.  Show all commits in target branch that are not in the reference branch

    ```
    git log <REF_BRANCH_NAME>..<TARGET_BRANCH_NAME>
    ```
    - The usual flags for `git log` are supported: `--oneline`, `--decorate`, `--graph`, etc.


Reference:
- <https://devconnected.com/how-to-compare-two-git-branches/>
