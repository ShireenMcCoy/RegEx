# Shireen's Guide to RegEx
A Regular Expressions cheat sheet

- **Literals** are just the exact string you're searching for.
- **Character Sets** go inside square brackets `[]`. `h[ai]ppy` can find "happy" or "hippy".
- **Ranges** `-` also go inside square brackets, and they include a hyphen.`[A-Za-z]` matches any uppercase or lowercase letter.
- The **caret symbol** `^`, when used inside square brackets before a character set, *excludes* that character set. `[^xyz]` matches any character that *isn't* x, y, or z.
- When the **caret symbol** / **hat** `^` is used at the start of a string (not inside brackets), it denotes that the string must **start** with whatever comes after the `^`. When it's used this way, it's called an **anchor**.
- The **dollar sign** `$` is also an anchor, but it's used at the *end* of a string to make sure that no more words come after the end of the string.
- The **period** `.` is a **wildcard** that can match any single character. `.at` can match "cat", "hat", "9at", and many other strings.
- The **backslash** `\` is an **escape character**. It's used before any character has a special meaning in RegEx, when you want to find the actual character. For example, if you want to find an actual period `.` rather than use it as a wildcard, you type `\.` Some other special characters that need to be escaped if you want to search for them are `^`, `$`, `?`, `*`, `+`, `{}`, `()`, `[]`, `-`, `|`, and `\`.
- The **pipe symbol** `|` is used for **alternation**. It basically means **OR**. So if you want to find "ice cream" OR "cake" (or both), you type `ice cream|cake`.
- **Parentheses** `()`are used for **grouping**. So if you want to find "I feel like ice cream" OR "I feel like cake", you would type `I feel like (ice cream|cake)`. If you don't use the parentheses and just type `I feel like ice cream|cake`, it will match both "I feel like ice cream", and also every instance of "cake" by itself.
- **Curly braces** `{}` are used to denote **fixed quantifiers**. They go after a character (or set, or range, or grouping) that you want to repeat a certain number of times. You can either put an exact quantity, like `{3}`, or a range of quantities, like `{2,5}` inside the braces. `ha{3,10}ha` means that the first "ha" must have at least three "a"s and at most ten "a"s.
- The **question mark** `?` matches the preceding character **0 or 1** times.
- The **asterisk** `*` matches the preceding character **0 or more** times. It's called the "Kleene star."
- The **plus sign** `+` matches the preceding character **1 or more** times. It's called the "Kleene plus."

**Shorthand Character Classes**
These character classes are a shorter way of writing some RegEx expressions:
- **`\w`** represents the RegEx range `[A-Za-z0=_]`: any upper or lowercase letter, any numeral, or an underscore. The "w" stands for **word**.
- **`\d`** represents the RegEx range `[0-9]`: any **digit** character.
- **`\s`** represents the RegEx range `[ \t\r\n\f\v]`: any white**space** character: a single space, tab, carriage return, line break, form feed, or vertical tab.

**Negated character classes** are all uppercase:
- **`\W`** is the **non-word** character class. It represents the RegEx range `[^A-Za-z0-9_]` -- in other words, any character that is *not* included in the `\w` range.
- **`\D`** is the **non-digit** character class. It represents any character that is not in the `\d` range.
- **`\S`** is the **non-whitespace** character class. It represents any character that is not in the `\s` range.

THE END!
