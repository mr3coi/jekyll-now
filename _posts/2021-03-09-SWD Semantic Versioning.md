---
published: true
layout: post
title: (SW Dev) Semantic versioning of software
---

A (widely accepted) way of assigning versions to softwares or libraries such that
change in version number carries a semantic message regarding the underlying API design.
- A version consists of 3 numbers with periods in between: `X.Y.Z` where each has a name as follows:
  1.  `X`: "major"
  2.  `Y`: "minor"
  3.  `Z`: "patch"

- An increase in `Z` indicates an API-unrelated update or a bug fix.
  There is no API change and thus no reason for the user to update his/her code.

- An increase in `Y` indicates a backward-compatible API change.
  A user can choose to update his/her code accordingly, but the code doesn't break either way.

- An increase in `X` indicates a breaking change in API, i.e. backward compatibility is not guaranteed anymore.
  A user has to adapt his/her code to the changed API so to use the given version of software or library.


References:
- <https://apifriends.com/api-management/what-is-semantic-versioning/>
