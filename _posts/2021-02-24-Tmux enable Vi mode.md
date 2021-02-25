---
published: true
layout: post
title: (Tmux) Enable Vi mode in window buffer
---

Enabling Vi mode in tmux allows for using Vi commands and hotkeys when navigating through
the window output buffer (entered by `<ctrl-b> [`).

1.  Enter `set-window-option -g mode-keys vi` into `.tmux.conf`.

2.  Restart tmux or reload `.tmux.conf`.

3.  In window buffer, one can now use functions such as the following:
    - `/<keyword>` to search for occurrences of `<keyword>`; use `n` and `N` to move between matches
    - Use `hjkl` to move cursor around
    - Use `gg` and `G` to move to the top and bottom of the buffer, respectively


Reference:
- <https://blog.sanctum.geek.nz/vi-mode-in-tmux/>
