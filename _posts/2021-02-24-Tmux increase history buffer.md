---
published: true
layout: post
title: (Tmux) Increase maximum length of history buffer
---

1.  Add `set -g history-limit N` to `.tmux.conf`, where `N` is a reasonable size positive integer.

2.  Restart tmux or reload `.tmux.conf` (refer to [this post](https://mr3coi.github.io/Tmux-disable-window-auto-renaming/) to find out how).


Reference:
- <https://unix.stackexchange.com/questions/43414/unlimited-history-in-tmux>
