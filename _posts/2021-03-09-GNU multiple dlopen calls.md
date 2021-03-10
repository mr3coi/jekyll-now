---
published: true
layout: post
title: (Vim) Set custom key mappings
---

1.  Use `nnoremap` to define macros that will be executed in **command mode**
    - Syntax: `nnoremap <KEY_ACTION> <ACTION_TO_TAKE>`
    - E.g.: Toggle NERDTree sidebar using `\\ + f`:
      ```
      nnoremap <Leader>f :NERDTreeToggle<Enter>
      ```
    - (Important) `<Leader>`: A "mapleader" variable, useful for defining custom mappings without
      collision with existing mappings (typically set to `\\`)
    - There are also different variants such as `cnoremap`, `vnoremap`, etc.;
      refer to `:help nnoremap` for details


2.  Symbol notations for non-letter keys provided by Vim
    - Notation provided to enhance readability of mapping definitions
    - E.g.: `<Space>`, `<Esc>`, `<Del>`
    - `<CR>`: Carriage Return (= `<Enter>`, `<Return>`)
    - Run `:help key-notation` to see a full list of such symbols


3.  Mappings predefined by Vim
    - E.g. `<C-r><C-w>` inserts the word currently under the cursor
      - E.g. Start off a global substitution command for exact matches of the word under cursor:
        ```
        nnoremap <Leader>s :%s/\<<C-r><C-w>\>/
        ```
    - `c_` prefix means that the mapping works in **c**ommand mode
    - Refer to `:help cmdline` for more details


4.  Use `:help <ITEM_TO_SEARCH>` to search for occurrence of `<ITEM_TO_SEARCH>` in Vim manual,
    e.g. `:help <Leader>`, `:help <C-r>`
    - `<ITEM_TO_SEARCH>` doesn't have to be a complete (key)word;
      lookup based on a part of (key)word is also supported


References:
- <https://stackoverflow.com/questions/1764263/what-is-the-leader-in-a-vimrc-file>
- <https://stackoverflow.com/questions/22142755/what-is-the-meaning-of-a-cr-at-the-end-of-some-vim-mappings>
- <https://vi.stackexchange.com/questions/22034/how-to-execute-with-call-and-c-r-matching>
