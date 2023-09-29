# Shorthand Character Classes

https://www.regular-expressions.info/shorthand.html


| Character | Meaning         | Description                    |
|-----------|-----------------|--------------------------------|
| `\d`      | `[0-9]`         | Matches a digit                |
| `\w`      | `[A-Za-z0-9_]`  | Matches a "word" character     |
| `\s`      | `[ \t\r\n\f]`   | Matches a whitespace character |

These can be used within character classes:
`[\s\d]` matches space followed by a digit.

### Negated character classes

The examples above can be capitalized to negate their meaning.

| Character | Meaning          | Description                       |
|-----------|------------------|-----------------------------------|
| `\D`      | `[^0-9]`         | Anything but a digit              |
| `\W`      | `[^A-Za-z0-9_]`  | Anything but a "word" character   |
| `\S`      | `[^ \t\r\n\f]`   | Anything but whitespace character |
