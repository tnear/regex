# Uppercase Transformation

An uppercase transformation, `\U`, transforms lowercase text into uppercase. The `\U` flag is used in the *replacement* text. `\E` is used to end (terminate) any uppercase or lowercase transformations. Many regular expression libraries do not support `\U` and `\L` (lowercase).

```
Input:       Hello world!
Pattern:     (.+)
Replacement: \U$1\E <- caps!
Result:      HELLO WORLD! <- caps!
```

*Note: `\E` is not necessary on all regular expression engines, including VSCode*

The pattern above collects all characters into the first capture group. The replacement uses `\U` to enable uppercase, then uses `$1` to reference the first capture group, then disables transformations with `\E`. Lastly, it appends some lowercase descriptor text.