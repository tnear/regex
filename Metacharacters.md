# Metacharacters

Metacharacters are characters which have a special meaning in regular expressions.

| Metacharacter | Description                                                         |
|---------------|---------------------------------------------------------------------|
| `.`           | Matches any character except a newline character.                   |
| `^`           | Matches the start of a string.                                      |
| `$`           | Matches the end of a string.                                        |
| `*`           | Matches 0 or more repetitions of the preceding regex.               |
| `+`           | Matches 1 or more repetitions of the preceding regex.               |
| `?`           | Makes the preceding character optional (matches 0 or 1 instances).  |
| `{n,}`        | Matches `n` or more occurrences of the preceding expression.        |
| `{n}`         | Matches exactly `n` occurrences of the preceding expression.        |
| `{n,m}`       | Matches between `n` and `m` occurrences of the preceding character. |
| `\\`          | Escapes the character following it.                                 |
| `[]`          | Character class. Matches any one of the enclosed characters.        |
| `\|`          | Alternator. Matches only one of the expressions                     |
| `()`          | Groups regular expressions.                                         |
| `\d`          | Matches any digit (equivalent to `[0-9]`).                          |
| `\D`          | Matches any non-digit character.                                    |
| `\w`          | Matches any word character (equivalent to `[a-zA-Z0-9_]`).          |
| `\W`          | Matches any non-word character.                                     |
| `\s`          | Matches any whitespace character (spaces, tabs, and newlines).      |
| `\S`          | Matches any non-whitespace character                                |
| `\b`          | Matches a word boundary                                             |
| `\B`          | Matches a non-word boundary                                         |