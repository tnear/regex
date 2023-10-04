# Backreference

Backreferences are used to match text which has been previously matched by a numbered capture groups. For example, `\1` references the first capture group, `\2` the second, and so on.

See [CaptureGroup](CaptureGroup.md) for an example.

## Examples

### Detect duplicated '#include' statements in a file

Pattern: `^(#include\s*<[^>]+>|#include\s*"[^"]+").*$(\n.*)*\1`

Explanation:
- Alternator for `#include <...>` and `#include "..."`.
- `.*$` matches rest of the line
- `(\n.*)*`: lazily matches any number of newlines followed by content. `\n` is needed to allow a search to span multiple lines (`.` does not match newlines)
- `\1`: backreference to match a duplicated `#include ...`