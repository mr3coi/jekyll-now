---
published: true
layout: post
title: (Tmux) Disable auto-renaming windows
---

1.  Add the following to `~/.tmux.conf` config file (create if not yet exists):

    ```
    set-option -g allow-rename off
    ```
   
2.  (If tmux is already running) source the updated config file to let it take effect

    Within tmux, enter the following into the command line (`<ctrl-B> :`):
    ```
    :source-file ~/.tmux.conf
    ```
    Or, run the following in shell:
    ```
    tmux source-file ~/.tmux.conf
    ```
    - Also possible to kill all open tmux sessions using `tmux kill-server`; use at user's risk


Reference:
- <https://stackoverflow.com/questions/6041178/keep-the-windows-name-fixed-in-tmux>
- <https://blog.sanctum.geek.nz/reloading-tmux-config/>
- <https://unix.stackexchange.com/questions/66606/tmux-not-sourcing-my-tmux-conf>
