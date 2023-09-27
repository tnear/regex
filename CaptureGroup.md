# Capture Group

Capturing groups are used for referencing or extracting the matched text. They are enclosed within parentheses `(...)` and can be referenced using a backreference.

Example: Remove consecutive duplicated words when both words begin with 'he'.

```
Input:       hello hello world
Pattern:     he(\w+) he\1
Replacement: he$1
Result:      hello world
```

The pattern looks for "he" then captures the rest of the word suffix using `(\w+)`. It then looks for a space followed by "he" and a backreference to the first capture group using `\1`.

The replacement text, `he$1`, removes the duplicate word by only inserting the capture group one time. To re-duplicate, you could make the replacement text `he$1 he$1`.