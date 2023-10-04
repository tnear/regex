# Recursion

Recursive regular expressions allow a regular expression pattern to repeat within itself, essentially applying recursion to regex. This is useful when dealing with nested patterns that have an indeterminate depth.

Recursive regular expressions are typically denoted by `(?R)`, `(?0)`, and `\g<0>`.

### Match same number of letter 'a' followed by 'z'

Pattern: `a(?R)?z`
