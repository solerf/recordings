+++
title = 'Gitr reset commit & keep changes'
date = '2025-10-31T23:15:22+01:00'
draft = false
tags = []
+++

When a commit is done by mistake or whatever to undo it but keep the changes, run:

```shell
git reset HEAD^

# or 

git reset HEAD~1
```

This moves the HEAD to point to the previous commit but keep the changes. 
For other cases just do an amend to continue editing the commit.
