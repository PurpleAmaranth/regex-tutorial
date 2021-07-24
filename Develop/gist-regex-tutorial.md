# Regex Gist

As a newbie starting to code, have you ever read someone's code and thought:

What is this garbage!?!! 

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

A seemingly random concatenation of otherwise meaningless cryptoid symbols smashed into a combinatorial line defining a function of crazy... but that is another story. 

Let's focus on this specific line first. This is definitely something you're going to want to know! This is a regex, or regular expression that allows coders to match specific contents of a string to something more valuable or useful to be read by our program. By using the components of the regex we can utilize this powerful method to make string utilization even easier. And that has countless applications!

This specific regex is useful for matching a URL. Yes, this seemingly random line of symbols helps our program identify a healthy and proper URL string. In this tutorial I will guide you through the breakdown of this regex and teach you how to use these expressions in the process.

## Summary

```
URL Regex:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`
```

When we look at this code snippet we can tell that there are a few distinguishable parts. In this tutorial I am going to break down each regex component to help you understand how this line identifies a URL string.

First we can tell there are initiating and terminating symbols like:
`/^` or `$/`
Pay attention to the `^` and `$`.

Then there are groupings of string characters like:
`'https'`
We all know this one!

There are even specific sets of characters like:
`[a-z\.]`
This seems like a range between a to z right?

Along with these more visible components we know there are things that **flag** symbols so that we know where to begin or end a match, and that these can be incorporated anywhere along the code. We also know we may need logical **operators** to translate symbols where we want to.

In this tutorial I will cover all of these concepts including **anchors**, **quantifiers**, **grouping constructs**, **bracket expressions**, **character classes**, operators like **OR operators**, **flags**, **escapes**, and more. Click on a link in the table of contents to go to that section.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Leggo My Eggo](#leggo-my-eggo)
- [Recommended Reading](#recommended-reading)

## Regex Components

### Anchors

**Definition:**

An anchor is a symbol that tags a position before, after, or inbetween a character or set of characters. An anchor is usually a carrot (`^`) or dollar sign (`$`).

**The URL Example:**

The `^` tags where we want the beginning of the line to be. So in this case we want the beginning of the line to start with a `/`
so we tag it with a carrot `/^`

Then the `$` tags where we want the end of the line to be. So in this case we want the end of the line to be more flexible, since the length of a URL is always variable based on some sort of file structure or pathing. We'll cover more on this soon! Hence we have `/?$/`

This code means we want something in slashes at the end, but it doesn't matter what it is exacly contained within the slashes.

### Quantifiers

**Definition:**
A quantifier specifies the numeric limit of characters we want to have. They usually apear in brackets like: `{1, 9}` meaning we want the string to have 1 to 9 characters within it.

```
Examples:
`*` --------- Match a patter 0 or more times.
`+` --------- Match a pattern 1 or more times.
`?` --------- Match a pattern 0 or only once. (Fewest times possible.)
`{}` -------- Match the set limit.
`{n}` ------- Match **exactly**  times.
`{n,}` ------ Match **at least** n times.
`{n, x}` ---- Match a pttern from min (n) to max (x).
```

**The URL Example:**

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

In the URL regex we can see that we want inbetween 2 to 6 characters from a-z here:

`([a-z\.]{2,6})`

### Grouping Constructs

**Definition:**
A grouping construct enables us to specify which characters we want to be read together. We can often group characters together by enclosing them withing parenthesis `()`. This is called a subexpression, and defines a mini-expression within the larger regex (reg. expression.) Got it?

**The URL Example:**

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

We can see that the groups we have in this regex are `(https?:\/\/)`, `([\da-z\.-]+)`, `([a-z\.]{2,6})`, and `([\/\w \.-]*)`. 

These subexpressions can also be called **capture groups** which are either capturing and non-capturing expressions. To capture a subexpression infers that we may want to store it for later use. To prevent storage we have to add `?:` to the expression within the parenthesis like this: `(?:Expression)`.

So none of these are non-capturing expressions.

### Bracket Expressions

**Definition:**

Anything contained in brackets is defining a range of alpabetic or numeric symbols.

```
For example:
`[a-z]` ---- is a string with any **lowercase** letter between a and z. To include uppercase we must write it differently.
`[a-zA-Z]`-- is a string with any **lower or uppercase** letters. Then, you guessed it...
`[A-Z]` ---- is any **uppercase** letter.
`[0-9]` ---- is any numeric symbol between 0 and 9.
`[_-]` ----- includes an underscore or hyphen.
```

We can also concatenate all of these expressions together to select wider ranges of symbols.

```
For example:
`[a-zA-Z0-9_-]` includes all of the above possibilities.
```

**The URL Example:**

```
`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`
```

So this means that in [\da-z\.-] and [a-z\.] we expect to have input with a range of symbols from a-z with other caveats. Keep reading!

### Character Classes

**Definition:**

A character class identifier defines a specific set of characters.

```
Some examples include:
`.` ---- Matches any character except '\n'.
`\d` --- Matches any integer between 0 and 9.
`\w` --- Matches and alpha numeric characer including a hyphen.
`\s` --- Matches any whitespace character like spaces, tabs, and breaks.
```

**The URL Example:**

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

```
We have two major class identifiers here:
`\d`,  which means to expect a decimal number or one digit from 0 to 9;
`\w`, which means to expect a **word character** which can contain a ASCII letter, digit, or underscore.
```

### The OR Operator

**Definition:**

Although it is not within our example URL regex I wanted to cover this important operator for you.

The OR Operator is denoted by '|'. We can use it to change a range of digits like `[abc]`, which will look for `'abc'`, into `(a|b|c)`. This will now accept `'abc'` as well as`'a'`, `'b'`, or `'c'`.

### Flags

**Definition:**

Although out URL example doesn't rely on flags, it is so important I wanted to include a couple of examples for you.

Flags are usually included at the end of the regex following second slash. They are used to give additional functionality to the regex serach or spcfiy it limits for what matches.

```
Examples:
`d` --- make indices for substring matches.
`g` --- make a global search.
`i` --- make a case-senstive search.
`m` --- make a multi-line search.
`s` --- allow '.' to match newline characters.
`u` --- treat patterns as unicode sequences.
`y` --- make a sticky search.
```

### Character Escapes

**Definition:**

The character escape is important to understanding character class assignments, and is something you'll want to read more about beyond the scope of this gist because it defines many very specific class designations that are useful tools in writing and understanding regex commands.

The basic denotation is a backslash '\'. This denotes a character that should be read literally and thusly many new definitions of character classes follow with the use of specific characters following the '\'. However, these definitions are not applied when contained within a parenthesis, but still work when contained within a bracket within a parenthesis.

**The URL Example:**

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

We can see our literals here: '\/\/' This means we expect a literal '/' here.

```
However for special chracters we have:
`\d`,  which means specifically a decimal number or one digit from 0 to 9;
`\.-`, which means specifically that a hypen needs to be escaped by the preceeding expression; and
`\w`, which means to expect a **word character** which can contain a ASCII letter, digit, or underscore.
```

### Leggo My Eggo

Now when we examine out URL regex we can see every component:

Take a look and see what you can recongnize now!

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

If you get stuck on a regex you can look them up on sites like regexr.com. Sites like this one break down the regex into its components and help you identify each individually.

Link: https://regexr.com/3um70

Thank you for reading my gist. I hop it has helped you understand a little bit more about regex and its use.

I have no idea why this section is named this way, but you should also consider looking into these concepts in your regex studies:

* Backreference Constructs
* Boundaries
* Lookaround Assertions

## Author

PurpleAmaranth is a Computer Science student at the Colorado School of Mines, working on her M.S. specializing in Robotics and Intelligent Systems.

You can reach her on GitHub: https://github.com/PurpleAmaranth.

## Recommended Reading

**developer.mozilla.org/:** 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#advanced_searching_with_flags
