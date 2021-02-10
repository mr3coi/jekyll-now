---
published: true
layout: post
title: (Github) Setting up automatic authentication using SSH
---

1.  Create SSH key using `ssh-keygen`:
    - Specify key type using `-t`; the following are recommended for safety:
        - `rsa` with RSA number at least 2048
        - `ed25519`
    - Add comment using `-C`
    - e.g. `ssh-keygen -t ed25519 -C "personal macbook"`
    - Follow instructions to generate public & private keys

2.  Add **public** key to Github user setting (under `Settings` -> `SSH and GPG keys`)
    - The whole public key line (**including** comment) should be pasted into Github

3.  If the generated key pair does NOT have default name (`id_XXX`, `id_XXX.pub` where `XXX` is the key type),
    create a file `~/.ssh/config` and write the following into it:
    ```
    Host github.com
        IdentityFile ~/.ssh/XXX
        User git
    ```
    where `XXX` is the non-default name of the key pair

4.  Check SSH connection via the following command: `ssh -T git@github.com`.
    Upon success, it should print a statement like the following:
    ```
    Hi <USERNAME>! You've successfully authenticated, but GitHub does not provide shell access.
    ```

5.  Unlike Gitlab, Github requires an extra step as noted in the statement above.
    Specifically, the remote repo URL needs to be updated as follows:
    ```
    git remote set-url <REMOTE_NICKNAME> git@github.com:<USERNAME>/<REMOTE_NAME>.git
    ```
    e.g. for remote repo `my_test_repo` owned by `my_account`:
    ```
    git remote set-url origin git@github.com:my_account/my_test_repo.git
    ```

6.  Do `git push` as usual


Reference:
- <https://gist.github.com/developius/c81f021eb5c5916013dc>
- <https://gist.github.com/xirixiz/b6b0c6f4917ce17a90e00f9b60566278>
- <https://stackoverflow.com/questions/14762034/push-to-github-without-a-password-using-ssh-key>
