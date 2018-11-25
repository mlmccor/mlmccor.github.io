---
layout: post
title:      "The Mysteries of Regex"
date:       2018-11-25 05:48:52 +0000
permalink:  the_mysteries_of_regex
---


Regex, short for Regular Expressions, is a system Ruby uses to specify patterns of a string for various uses. You can use Regex to change certain words or characters in a string, split a string into an array in specific places, or even to see if the string is valid for your purpose (like detecting an valid email address or if a phone number has enough numbers in it). Although, to the untrained eyes, it will just look like a ton of random characters. To me, Regex seems a lot like magic spells. Seemingly random words that, when used in the correct order, do something powerful, but said slightly incorrectly or in the wrong order, do absolutely nothing except make you look foolish. Here's some tips to demystify Regex and to get you  started with this tool.

## The Slashes (//)

Regex is usually expressed between two forward slashes `//`, with the only exception I've found is when using it in a #split method.

```
string.match(/\s*[-.]\s*/)

string.split(%r{\s*[-.]\s*})
```

The #match method uses the Regex in it's normal form, while the #split method uses the %r{ } to utilize Regex. Both uses should be learned in order to utilize Regex fully.

## The types of expressions

The easiest way to get a handle on Regex commands are knowing the different types of commands and the rules that follow them. This will give you a better idea of what is possible with Regex and how you can use it. I am completely aware that this is not a complete list of the types of expressions, just the most common ones used in my experience.

#### String literals

One possible use for Regex is simply the literal string value you're searching for:

```
text = "I need to go to the grocery store"

text.scan(/grocery/)

# returns [grocery]
```

If you're looking to match specific words with your Regex, this is definitely the simplest and most straightforward method.


#### Brackets and Ranges

By using the brackets `[ ]` you can use a single character from a collection. Say we wanted to select any word that started with a vowel.

```
text = "I want eggs and bacon for breakfast"

text.scan(/\b[aeiou]\w*/)

# returns ["eggs", "and"]
```

Using the `^` right after the opening bracket will reverse the use of the bracket and find any character **except** those in the brackets.

In these brackets, the use of range characters will greatly assist anyone who needs to find a broad range of characters:

* [a-z]- matches **lowercase** letters a through z.
* [A-Z]- matches **uppercase** letters A through Z.
* [0-9]- matches numbers 0-9
* . - matches any character (to match a literal period, you would need to use an "escape" slash: `\`)

Once again, the `^` will match any numbers/letters outside of the specified range.


#### Escaped Commands

Escaped commands are commands that use the backslash `\` character. These include a wide variety of useful commands like:

* \s - any "whitespace" character (a normal space, tabs, or a line break)
* \d - any digit
* \w - any "word character" (letter, number, or underscore)
* \b-  any word boundary (space surrounding a word) (This doesn't include before the first character and after the last character)

Capitalizing any of letters in these expressions will **reverse** the command, like the carrot before.

Let's look at our earlier Regex example: `/\b[aeiou]\w*/`

The full breakdown of this Regex is that it's looking for a vowel `[aeiou]` that occurs after a word boundary `\b` follwed by an optional number of word characters `\w*`. The * character will be covered more in the next section. 


#### Quantifiers

Quantifiers allow a shorthand method to use multiple commands. They always affect the command before they are shown. 

* x? - Zero or one of x
* x* - Zero or more of x
* x+ - One or more of x
* x{5} - 5 of x
* x{5,9} - Between 5 and 9 of x

In our earier example: `/\b[aeiou]\w*/` we used the star `*` after the `\w` to allow for zero or more word characters to follow the vowel. This is what allows our Regex example to select the entire word of any size that starts with a vowel.


This is only a brief example of Regex commands that I've found to be the most common ones used. Hopefully you start to see the patterns of Regex examples as well as the possibilities for their use in your code. If you aren't already  aware of it, [Rubular](http://rubular.com) is a great tool for testing Regex expressions against strings. It even has more great commands for it! 
