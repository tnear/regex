# Character Classes

https://www.regular-expressions.info/charclass.html

Character classes, enclosed in `[]`, tell the regex engine to match one of the characters. For example, `gr[ae]y` matches `gray` or `grey`.

### Ranges
The `-` character creates ranges. For example, `[a-zA-Z0-9]` matches alphanumeric.

### Negated character classes
Use `^` as the first charcter in brackets to negate matches. To match anything which is *not* a digit, use `[^0-9]`.

### Escaping metacharacters
The characters `]`, `^`, and `-` have special meaning inside character classes. To escape them, use `\`. For example, this matches any of the three metacharacters: `[\]\^\-]`.

Additionally, the `-` character can be placed at the beginning or end of the character class list unescaped. This matches lowercase or `-`: `[a-z-]`.
