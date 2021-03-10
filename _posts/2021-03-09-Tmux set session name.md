---
published: true
layout: post
title: (Tmux) Set the name of a session
---

1.  The same file handle is returned multiple times.
    - If the path provided to `dlopen` differs (even when the absolute path is the same),
      different file handles are returned.

2.  A reference count is maintained by the dl library,
    so a dynamic library needs to be closed as many times using `dlclose`
    as it has been opened using dlopen.
    - The dynamic library is unloaded only when the reference count drops to 0
      (+ no other loaded libraries use its symbol).

3.  `dlopen` with `RTLD_NOLOAD` flag can be used to 
    `dlopen` with `RTLD_NOLOAD` returns `NULL` if the target library is not resident on memory,
    or the handle of the library if it is resident.
    This can be used to:
    - avoid `dlopen` from opening the same library more than once
    - check whether the reference count has dropped to 0. E.g.:
      ```
      // NOTE: Below code has not been tested
      while ((void *handle = dlopen(TARGET_LIB_PATH, RTLD_NOLOAD)) != NULL)
      {
          dlclose(handle);
      }
      ```


References:
- <https://stackoverflow.com/questions/12148454/will-dlopen-yield-the-same-handle-for-two-calls-with-the-same-file>
- <https://stackoverflow.com/questions/8033481/is-there-a-way-to-find-out-the-number-of-references-to-a-dynamic-library-in-a-pr>
