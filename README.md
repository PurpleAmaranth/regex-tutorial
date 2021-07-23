# 17 Computer Science for JavaScript: Regex Tutorial

## Description

This is a short tutorial on regex code.

This tutorial explains how a specific regular expression, or regex functions by breaking down each part of the expression and describing what it does. Enjoy following the walkthrough and learning to improve your code!

## User Story

```md
AS A web development student
I WANT a tutorial explaining a specific regex
SO THAT I can understand the search pattern the regex defines
```

## Link

Gist Link: https://gist.github.com/PurpleAmaranth/140e85cf56b22520afc0f8a7c934c83a

## Instructions

```md
Read the regex-tutorial gist!
Contents:
There is a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the regex featured in the tutorial, a table of contents linking to different sections that break down each component of the regex and explain what it does, and a section about your author with a link to the author’s GitHub profile.

You can click on the links in the table of contents
and be taken to the corresponding sections of the tutorial.
Read through each section of the tutorial to find 
a detailed explanation of what a specific component of the regex does.
Once you reach the end of the tutorial if you have more questions
you can find my contact information in the author section and a link to my GitHub profile.
```

## More about Regex:
## What Is a Regex?

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 

For example, the following regular expression can be used to verify that user input is a valid email address:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the `@` symbol, followed by a domain.

Before you get started, watch this [introduction to regular expressions video](https://youtu.be/7DG3kCDx53c) and read [Regex Tutorial: Matching a Username](http://coding-boot-camp.github.io/full-stack/javascript/regex-tutorial) to learn how to identify the different components that make up a regex. If you need any additional help, there are many resources on the web. Feel free to do your own research to find one that can help you complete this assignment.

Once you have a better understanding of what these different parts of a regular expression do, you’ll need to explain what they do for a specific regex.

You can choose one of the following regular expressions or you can choose one that you found on your own (with the exception of the one that is covered in the [Regex Tutorial: Matching a Username](http://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial):

* Matching a Hex Value: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

* Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

* Matching a URL: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

* Matching an HTML Tag: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`
