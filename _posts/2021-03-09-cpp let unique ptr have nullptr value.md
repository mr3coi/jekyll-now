---
published: true
layout: post
title: (C++) Letting `unique_ptr` have `nullptr` value
---

Setting a `unique_ptr` to `nullptr` is supported by C++11 standard.

1.  Declaring a `unique_ptr` without definition fills the pointer with `nullptr`


2.  `unique_ptr` has dedicated overloaded assignment operator to update its value
    - The object previously pointed to by the pointer is destroyed
    - Effectively equivalent to `unique_ptr::reset()` with no argument


References:
- <https://stackoverflow.com/questions/15070862/can-a-unique-ptr-take-a-nullptr-value>
- <https://en.cppreference.com/w/cpp/memory/unique_ptr/reset>
