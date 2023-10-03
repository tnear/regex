# Capture Group

Capturing groups are used for referencing or extracting the matched text. They are enclosed within parentheses `(...)` and can be referenced using a backreference.

Example: Remove consecutive duplicated words when both words begin with 'he'.

```
Input:       hello hello world
Pattern:     \bhe(\w+) he\1\b
Replacement: he$1
Result:      hello world
```

The pattern looks for "he" then captures the rest of the word suffix using `(\w+)`. It then looks for a space followed by "he" and a backreference to the first capture group using `\1`.

The replacement text, `he$1`, removes the duplicate word by only inserting the capture group one time. To re-duplicate, you could make the replacement text `he$1 he$1`.

### Non-capture group
Use `(?:<expression>)` to create a non-capturing group. These are most useful when you want `()` to group the expression, but do not need to capture the contents.

### Named capture group
Named capture groups use this syntax
```
Pattern:      (?P<name>group)
Substitution: $name
```

#### Example: change "hello world" to "hello all":
```
Input:        hello world
Pattern:      (?P<name>hello) world
Substitution: $name all
Output:       hello all
```

### Branch reset group
The syntax `(?|...)` creates a branch reset group. The pattern `(?|(a)|(b)|(c))` creates one capture group with three alternatives. The capture group number `$1` holds `a`, `b`, or `c`. 

This is in contrast with the pattern `(a)|(b)|(c)` which creates three capture groups.

The pattern `(?|(a)|(b)|(c))\1` will match `aa`, `bb`, or `cc`.