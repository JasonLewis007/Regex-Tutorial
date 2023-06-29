# Challenge 17 Computer Science for JavaScript Challenge

## Summary
In this tutorial, we will delve into using regular expressions (regex) to match and search for Url addresses within text. We'll provide a detailed breakdown of each component of a regex expression designed to match valid Url addresses, helping you grasp the workings of a typical Url regex pattern.

Let's examine the regex pattern used to validate Url addresses, as shown in the code snippet below:

const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;

This regex pattern serves to ensure that Url addresses adhere to a specific format.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)


### Anchors
In the regular expression `const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, there are two anchors used:

1. `^` (caret) - Start of Line Anchor:
   The caret `^` at the beginning of the regex pattern signifies that the match should start at the beginning of the string. It ensures that the pattern that follows it is found at the start of the string.

2. `$` (dollar sign) - End of Line Anchor:
   The dollar sign `$` at the end of the regex pattern denotes that the match should end at the end of the string. It ensures that the pattern that precedes it is found at the end of the string.

Together, these anchors `^` and `$` ensure that the entire string is matched by the regex pattern, rather than just a substring within the string. They define the boundaries within which the pattern should be found.

The regex pattern `^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$` is used to validate URLs. The anchors `^` and `$` ensure that the pattern matches the entire string and not just a part of it.


### Quantifiers
 In the regular expression`const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, there are several quantifiers used.

1. `?` - Optional quantifier:
   The `?` quantifier is used after `(https?:\/\/)` to indicate that the preceding `s` (for "https") is optional. It allows the URL to start with either "http://" or "https://".

2. `*` - Zero or more quantifier:
   The `*` quantifier is used after `([a-zA-Z0-9-]+\.)` to specify that the preceding group, `[a-zA-Z0-9-]+\.`, can repeat zero or more times. It allows for subdomains in the URL.

3. `+` - One or more quantifier:
   The `+` quantifier is used after `[a-zA-Z0-9-]+` to specify that the preceding character class should occur one or more times. It ensures that there is at least one character in the domain name.

4. `{2,}` - At least two quantifier:
   The `{2,}` quantifier is used after `[a-zA-Z]{2,}` to indicate that the preceding character class should occur at least two times. It ensures that the top-level domain (TLD) consists of two or more consecutive alphabetical characters.

5. `*` - Zero or more quantifier:
   The `*` quantifier is used after `(\/[^\s]*)` to specify that the preceding group, `\/[^\s]*`, can repeat zero or more times. It allows for an optional path component in the URL.

Quantifiers allow you to specify the number of occurrences of a preceding element in a regular expression. They control the matching behavior and repetition of characters or groups.

### Grouping Constructs
 In the regular expression `const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, there are grouping constructs used to group parts of the regular expression. 

1. `(https?:\/\/)`
   This is a capturing group that encloses `https?:\/\/`. It captures the protocol part of the URL (http:// or https://) if present. The captured value can be accessed separately if needed.

2. `([a-zA-Z0-9-]+\.)`
   This is another capturing group that encloses `[a-zA-Z0-9-]+\.`, which represents the subdomain part of the URL. It captures the subdomain and the trailing dot if present. The captured value can be accessed separately if needed.

3. `(\/[^\s]*)`
   This is a capturing group that encloses `\/[^\s]*`, which represents the optional path part of the URL. It captures the forward slash `/` followed by any non-whitespace characters if present. The captured value can be accessed separately if needed.

Grouping constructs allow you to group parts of the regular expression together, apply quantifiers to the entire group, or capture specific portions of the matched text for further use. They provide control over the logical grouping and manipulation of the pattern.

### Character Classes
In the regular expression `const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, there are several character classes used.

1. `[a-zA-Z0-9-]`:
   This character class matches a single character that can be any uppercase or lowercase letter (`a-z`, `A-Z`), digit (`0-9`), or hyphen (`-`). It is used in multiple places within the pattern to define valid characters in different parts of the URL.

2. `[a-zA-Z]`:
   This character class matches a single alphabetical character, either uppercase or lowercase. It is specifically used to validate the top-level domain (TLD) part of the URL.

3. `[^\s]`:
   This is a negated character class, indicated by the caret `^` at the beginning. It matches any character that is not a whitespace character. It is used to validate the optional path component of the URL, ensuring that it doesn't contain any spaces.

Character classes allow for specifying the range of acceptable characters in different parts of the URL pattern. They contribute to the validation and matching of URLs based on the defined character sets.

### The OR Operator

In the regular expression `const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, the "or" operator is represented by the pipe symbol `|`.

The regular expression focuses on validating URLs and does not utilize the "or" operator in this context. Instead, it utilizes other constructs like character classes, quantifiers, and anchors to define the pattern for matching valid URLs.

### Flags
In the regular expression`const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, there are no flags specified. Flags in regular expressions are optional parameters that modify the behavior of the pattern matching. They are typically added after the closing delimiter of the regular expression, which is `/` in this case.

Here are some commonly used flags in regular expressions:

1. `i` - Case-insensitive flag:
   When `i` flag is used, the pattern matches both uppercase and lowercase letters interchangeably. For example, `/pattern/i` would match "Pattern", "PATTERN", "pattern", and so on.

2. `g` - Global flag:
   The `g` flag enables global matching, which means that the pattern is applied to the entire string and not just the first match. It allows multiple matches to be found. For example, `/pattern/g` would find all occurrences of "pattern" in the string.

3. `m` - Multiline flag:
   The `m` flag is used for multiline matching. It changes the behavior of anchors (`^` and `$`), making them match the start and end of each line in a multiline string, rather than the start and end of the entire string.

### Character Escapes
 In the regular expression`const urlRegex = /^(https?:\/\/)?([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.[a-zA-Z]{2,}(\/[^\s]*)?$/;`, there are no explicit character escapes. 

Character escapes are special sequences that begin with a backslash `\` and are used to represent specific characters or character classes. They provide a way to match characters that have special meanings in regular expressions or to represent characters that cannot be directly expressed.

Here are some common character escapes:

1. `\d` - Matches any digit character (equivalent to `[0-9]`).
2. `\w` - Matches any word character (alphanumeric character or underscore).
3. `\s` - Matches any whitespace character (spaces, tabs, line breaks, etc.).
4. `\D` - Matches any non-digit character (equivalent to `[^0-9]`).
5. `\W` - Matches any non-word character (equivalent to `[^A-Za-z0-9_]`).
6. `\S` - Matches any non-whitespace character.
7. `\.`, `\-` - Escapes a period and hyphen to match them as literal characters rather than their special regex meanings.



## Author

My name is Jason Lewis and I am an aspiring Full Stack Developer enrolled in University of North Carolina Charlotte Full Stack Bootcamp.  My GitHub Profile:  https://github.com/JasonLewis007
