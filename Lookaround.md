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

