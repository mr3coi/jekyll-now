---
published: true
layout: post
title: (Git) Create & apply patch
---

1.  Create git patch file:
    After making changes to source code, write contents of `git diff` to a file:
    ```
    git diff [--cached] [<SOURCE_FILE_SUBSET>] > <PATCH_FILE_PATH>
    ```


2.  Apply the patch file in another branch where needed: `git apply <PATCH_FILE_PATH>`


References:
- <https://www.specbee.com/blogs/how-create-and-apply-patch-git-diff-and-git-apply-commands-your-drupal-website>
