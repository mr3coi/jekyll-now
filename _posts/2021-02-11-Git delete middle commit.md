---
published: true
layout: post
title: (Git) Edit/delete an in-the-middle commit from history
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
    Change `pick` to `drop` to remove (or edit) a past commit (or `edit` if wishing to update
    a commit changes, and `reword` to update a commit message).
    - When `edit`ing, make changes to code and stage them, then run `git rebase --continue`.
    - NOTE: To edit the most recent, not-yet-pushed commit, just use `git commit --amend`.


Reference:
- <https://www.w3docs.com/snippets/git/deleting-commits-from-a-branch-in-git.html>
- <https://docs.github.com/en/github/committing-changes-to-your-project/changing-a-commit-message>
