# Recursion

Recursive regular expressions allow a regular expression pattern to repeat within itself, essentially applying recursion to regex. The main purpose of recursive regular expressions is to match balanced or nested patterns.

Recursive regular expressions are typically denoted by `(?R)`, `(?0)`, and `\g<0>`.

### Match same number of letter 'a' followed by 'z'
```
Pattern: a(?R)?z
Matches: az, aazz, aaazzz, ...
```

For the string `aaazzz`, the engine first matches `a` then encounters `(?R)`. This says to start matching the pattern again *after* the first a. The 2nd character is `a` which again matches, then the engine proceeds to `(?R)` and repeats the process for the 3rd `a`.


### Match balanced parentheses with 0+ characters in between
```
Pattern: \((?>[^()]|(?R))*\)
Matches: (a), (ab(c)d), ((())())
```