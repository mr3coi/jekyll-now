---
published: true
layout: post
title: (Vim) Commands for managing tabs
---

Execute the following in command mode:
1.  Open `FILE` on a new tab: `:tabe[dit] <FILE>`

2.  Reposition tab among other tabs
    - Move tab to $$i^{th}$$ position: `tabm[ove] <i>`
    - Move tab relatively $$i$$ times to the **right**: `tabm[ove] +<i>`
    - Move tab relatively $$i$$ times to the **left**:  `tabm[ove] -<i>`

3.  Close a tab with multiple splits (`:q` will close only a single split): `:tabc[lose]`

Reference:
- <https://stackoverflow.com/questions/32714834/how-to-close-a-tab-in-vim/32715229>
