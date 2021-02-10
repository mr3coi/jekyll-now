---
published: true
layout: post
title: (Vim) commands :s, :g, :v
---

1.  `:s`: Substitution
    - Syntax: `:[range]s/pattern/relacement[/gci]` where
    - Flags: `gci`
        - `g`: Catch & substitute all matches in a given line,
               not just the first ("**G**lobal")
        - `c`: Ask user whether to substitute or not ("**C**onfirm")
        - `i`: Match pattern in case-**I**nsensitive manner
    - e.g. `:s/apple/banana/c` substitutes the first "apple" in each line to "banana"
           after user confirmation

2.  `:g`: Global command
    - Syntax: `:[range]g/pattern/cmd` where
        - `pattern`: (Regex) pattern to match a given line
        - `cmd`: Command to execute on each matched line
    - e.g. `:g/^\t\t/d` deletes all lines starting with 2 tabs

3.  `:v`: Global non-match command

4.  Other tips
    - Wrapping a word or phrase with `\<`, `\>` forces to match
      that word or phrase exactly (occurrence as partial words are ignored)


Reference:
- <https://vim.fandom.com/wiki/Power_of_g>
- <https://vim.fandom.com/wiki/Search_and_replace>
