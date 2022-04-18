# Regex Tutorial

This Regex (Regular Expression) tutorial is created to help you understand and define the sequence of special characters to verify a search term. A Regex is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also used frequently to validate input data.

## Summary

Today I will be covering and breaking down the components of a regular expression used to match Hex Values. Hex values are commonly used for color using the hexadecimal color code format. In the web we can use hex triplet (hex color code) to represent colors on a web page. For the hex color code, there are two formats, a standard hex triplet and a shorthand hex format, where both formats start with a **#**.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

`/^`#?([a-f0-9]{6}|[a-f0-9]{3})`$/`

The first component that we will be breaking down are the anchors. As shown in the highlighted portion of our regular expression, the components that are highlighted are what we call anchors. Anchors are used at the start and end of a string or expression. In this case `/^` and `$/` signify the beginning or end of our expression.

### Quantifiers

/^#`?`([a-f0-9]`{6}`|[a-f0-9]`{3}`)$/

Next we will be covering quantifiers. Quantifiers are used to communicate how many characters are expected. Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. By default, quantifiers are greedy, and will match as many characters as possible. If the "*,+,?,{}"* characters are found within regular expressions, they are considered quantifiers. The `?` indicates the expression to match 0 or 1 time. As mentioned in the summary above because there are 2 types of formats we'll use the or operator to distinguish which format we are using. In our Hex Value regular expression we have `{6}` (Hex Triplet Format) and `{3}` (Shorthand Hex Format), this indicates that the length of the component preceding these quantifiers should be 6 for `{6}` and 3 for `{3}`. 

Hex Triplet Formats Include:
#000000, #FFFFFFF, #0099CC

Shorthand Hex Format:
#000, #FFF, #09C
(the hex triplet format would just double each character: #09C -> #0099CC)

### OR Operator

/^#?([a-f0-9]{6}`|`[a-f0-9]{3})$/

The next component we will be discussing is the "or" operator. The "or" operator within a regular expression is defined using the `|` element. The or operator indicates that it could either of the components that we are separating with the `|`. For our hex value regular expression we have ([a-f0-9]{6}`|`[a-f0-9]{3}). Note the or operator separating these 2 components. This means that our hex value could either be 6 characters `[a-f0-9]{6}` or 3 characters `[a-f0-9]{3}`.

### Character Classes

/^#?(`[a-f0-9]`{6}|`[a-f0-9]`{3})$/

Next we will be discussing character classes. Character classes are components within our regular expression that tells us what type of characters to expect. In our example our character classes are confined within brackets `[]`. For our example we have 2 character classes: `[a-f0-9]` and `[a-f0-9]` which searches for the same values. We will be breaking down what the characters are searching within these character classes. `a-f` searches for letters *a-f* and `0-9` searches for digits *0-9*.

### Bracket Expressions

/^#?`([a-f0-9]{6}|[a-f0-9]{3})`$/

Bracket expressions in our regular expression signify the beginning of a character class or quantifier statement. In our example we use parenthesis to define our bracket expressions.

### Greedy and Lazy Match

/^#`?`([a-f0-9]{6}|[a-f0-9]{3})$/

In this section we will discuss greedy and lazy matches. A greedy match tries to match an element as many times as possible. Whereas, a lazy match tries to match an element as few times as possible. In our example we have `?` which signifies lazy quantifier. This is referred to a lazy quantifier because it causes the regular expression engine to match as few occurances as possible. We can simply turn this lazy match into a greedy one by adding a `?`.
