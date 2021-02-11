---
published: true
layout: post
title: (Git) Delete an in-the-middle commit from history
---

1.  Safe approach: Revert

    ```
    git revert <sha1-commit-hash>
    ```
    where the hash is of the commit to revert.
    This creates a new commit with all the previous commit changes undone.
   
2.  Unsafe approach: Interactive rebase

    ```
    git rebase -i <sha1-commit-hash>
    ```
    where the hash points to a successful commit
    prior to the commit to be deleted.
    This brings up an editor where each commit following the hash commit above is listed.
    Earlier commit (one closer to the hash commit) is at the top of the editor page.
    Change `pick` to `drop` (or `edit` if wishing to edit) to remove (or edit) a past commit.


Reference:
- <https://www.w3docs.com/snippets/git/deleting-commits-from-a-branch-in-git.html>
