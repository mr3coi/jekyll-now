---
published: true
layout: post
title: (Git) Fetching & building a branch from fork
---

1.  Fetch ONLY a specific branch from a fork repo:
    ```
    git remote add <FORK_NICKNAME> <PATH/TO/FORK>
    git fetch <FORK_NICKNAME> <BRANCH_TO_FETCH>
    ```

2.  Undo all fetches from the fork:
    ```
    git remote remove <FORK_NICKNAME>
    ```

3.  Disable accidental push to the fork by setting push URL of the fork remote to a dummy value:
    ```
    git remote set-url --push <FORK_NICKNAME> no_push
    ```
    - `"no_push"` has no meaning here; just some non-URL


References:
- <https://stackoverflow.com/questions/35591887/how-to-undo-git-fetch>
- <https://stackoverflow.com/questions/10260311/git-how-to-disable-push>
