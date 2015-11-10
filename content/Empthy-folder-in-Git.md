---
title: Git - Empthy folder in Git
author: Tim Kleinschmidt
date: 2012-05-31 17:25
category: Git
---

**How do I add an empty directory to a git repository**

The solution is:

``` git
# Ignore everything in this directory
*
# Except this file
!.gitignore
```

**For your interest:**

[Stackoverflow Question]

[Stackoverflow Question]: http://stackoverflow.com/questions/115983/how-do-i-add-an-empty-directory-to-a-git-repository/
