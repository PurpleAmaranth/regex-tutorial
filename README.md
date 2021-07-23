# Computer Science for JavaScript: Regex Tutorial

## Introduction

As a newbie starting to code, have you ever read someone's code and thought:

What is this garbage!?!! 

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

## Description

This is a short tutorial on a specific regex code. I'm going to go over the mysterious object you see above and make it less ambiguous.

This tutorial explains how a specific regular expression, or regex functions to match a URL or other strings by breaking down each part of the expression and describing what it does. Enjoy following the walkthrough and learning to improve your code by incorporating regex like never before!

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
There is a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the URL regex featured in the tutorial, a table of contents linking to different sections that break down each component of the URL matching regex, an explanation of what it does, and a section about your author with a link to the author’s GitHub profile.

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

## Recommended

Before you get started, watch this [introduction to regular expressions video](https://youtu.be/7DG3kCDx53c) and read [Regex Tutorial: Matching a Username](http://coding-boot-camp.github.io/full-stack/javascript/regex-tutorial) to learn how to identify the different components that make up a regex. If you need any additional help, there are many resources on the web.

Once you have a better understanding of what these different parts of a regular expression do, you’ll be able to incorporate them into your own code!

We will specifically cover the following:

* Matching a URL: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

