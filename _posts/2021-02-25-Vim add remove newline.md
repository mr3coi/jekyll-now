---
published: true
layout: post
title: (Vim) Replace / replace with newlines
---

1.  Replace newlines to XX: `:%s/\n/XX/`
    - Replace the above `%` with a range to apply the replacements only to a specific range

2.  Replace XX with newlines: `:%s/XX/\r/`
    - Replace the above `%` with a range to apply the replacements only to a specific range
    - Note the use of `\r` instead of `\n` this time


Reference:
- <https://www.linuxquestions.org/questions/linux-newbie-8/vim-remove-line-breaks-757993/>
