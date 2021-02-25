---
published: true
layout: post
title: (Vim) resize, rearrange splits
---

1.  Resize splits: `:[vertical ]resize [+-]N`
    - `resize`: sets (or increments/decrements) the height of the window to (by) `N` rows
    - `vertical resize`: sets (or increments/decrements) the width of the window to (by) `N` columns

2.  Rearrange splits: `<ctrl-w> HJKL`
    - Moves the split that I am currently in towards the specified direction
    - NOTE: The directions are capitalized (i.e. `<shift-hjkl>`)
    - TIP: Close `NERDTree` split before moving splits around, turn it back on later
      (since `NERDTree` will be moved around too)


Reference:
- <https://superuser.com/a/223951>
- <https://vim.fandom.com/wiki/Resize_splits_more_quickly>
