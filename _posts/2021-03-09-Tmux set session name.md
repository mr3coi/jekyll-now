---
published: true
layout: post
title: (Tmux) Set the name of a session
---

1.  Create a new session with customized name: `tmux new -s <SESSION_NAME>`
    - By default, tmux sessions are assigned increasing non-negative integers as names
    - However, unlike how windows have unique, persistent indices,
      the non-negative integers are NOT indices and are lost after a session is renamed


2.  Update existing session name: `<Ctrl-b> + $`, then enter the new name in the prompt below


3.  Attach to a session with updated name: `tmux a[ttach] -t <UPDATED_SESSION_NAME>`


References:
- <https://blog.tinned-software.net/manage-terminal-sessions-with-tmux/#:~:text=When%20connected%20to%20the%20tmux,enter%20to%20change%20the%20name.>
