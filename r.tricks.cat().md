---
id: r876xjhay81os40kbfwyjgb
title: cat()
desc: 'output objects of an atomic vector, concatenating the representations'
updated: 1650257909249
created: 1650257554083
---

Use the fucntion `cat` when wanting to concanate objects from an atomic vector.

### Important arguments

- sep: a character vector of strings to append after each element. For example `sep = "\n"` outputs one object per line.

### Details

`cat` is useful for producing output in user-defined functions. It converts its arguments to character vectors, concatenates them to a single character vector, appends the given `sep =`  string(s) to each element and then outputs them.

Source: https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/cat