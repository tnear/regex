# Lookaround

Lookahead and lookbehind look before or after patterns but do not consume any characters.

### Positive lookahead
Syntax: `(?=...)`

#### Match 'hello' only when followed by 'world':
```
Input:   hello world hello all
Pattern: hello (?=world)
Match:   first 'hello ' but not second
```

### Negative lookahead
Syntax: `(?!...)`

#### Match 'hello' when it is NOT followed by 'world':
```
Input:   hello world hello all
Pattern: hello (?!world)
Match:   second 'hello ' but not first
```

### Positive lookbehind
Syntax: `(?<=...)`

#### Match 'world' when it is preceded by 'hello':
```
Input:   hello world the world
Pattern: (?<=hello) world
Match:   first ' world' but not second
```

### Negative lookbehind
Syntax: `(?<!...)`

#### Match 'world' when it is NOT preceded by 'hello':
```
Input:   hello world the world
Pattern: (?<!hello) world
Match:   second ' world' but not first
```

## Examples

### Find 6-letter words containing 'cat'
https://www.regular-expressions.info/lookaround2.html

Pattern: `(?=\b\w{6}\b)\w*cat\w*`

The lookahead finds 6 letter words. The rest of the pattern looks for `cat` between word characters. Because lookaround consumes no characters, the pattern will only match when both `\w+` matches sum to 3 characters (plus 3 characters for 'cat').

*The end of the pattern above can be optimized to `\w{0,3}cat\w*` to reduce backtracking. The `{0,3}` portion encompasses all lengths the left side can have given that 'cat' consumes 3 of the 6 allowed characters.*

More complex problem:

Find words 4+ characters in length containing 'cat' or 'dog'.

Pattern: `(?=\b\w{4,}\b)(\w*(cat|dog)\w*)`

- `{4,}`: finds 4+ length
- `(cat|dog)` match 'cat' or 'dog'