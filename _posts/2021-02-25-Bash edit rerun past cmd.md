---
published: true
layout: post
title: (Bash) Edit and re-run a past command
---

1.  Quick way for the **last** cmd: `^<PART_TO_REPLACE>^<NEW_PART>`
    - E.g. re-running the past command with "debug" instead of "release": `^release^debug`
    - NOTE: Only the first occurrence of `<PART_TO_REPLACE>` is replaced;
      for multiple substitutions, use the generalized version below

2.  More general syntax: `!<CMD_NUM>:gs/<PART_TO_REPLACE>/<NEW_PART>`
    - E.g. re-running the past command with "debug" instead of "release" on the last cmd:
      `!!:gs/release/debug`
    - E.g. re-running the past command with "debug" instead of "release" on cmd #1043:
      `!1043:gs/release/debug`
    - `g`: Global substitution (substitute all occurrences of `<PART_TO_REPLACE>`
    - `s`: Substitution
    - Cmd number can be found out using `history` cmd


Reference:
- <https://unix.stackexchange.com/questions/243317/bash-how-can-i-replace-a-string-in-a-previous-command>
