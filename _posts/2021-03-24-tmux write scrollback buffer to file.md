---
published: true
layout: post
title: (Tmux) Write scrollback buffer contents to file
---

Execute the following after the Tmux prefix (`ctrl+b` by default):
1.  Capture scrollback buffer contents:
    `:capture-pane -S -<NUM_LINES_TO_CAPTURE>`

2.  Write captured contents to file:
    `:save-buffer <OUTPUT_FILE_PATH>`


References:
- <https://unix.stackexchange.com/questions/26548/write-all-tmux-scrollback-to-a-file>
