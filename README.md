# learn-markdown
examples for markdown language, for original and detail reference please see
[here](https://daringfireball.net/projects/markdown/syntax) or [here](http://wowubuntu.com/markdown/)
## AUTOMATIC ESCAPING FOR SPECIAL CHARACTERS
if you want to include a copyright symbol in your article, you can write:
&copy;

and Markdown will leave it alone. But if you write:
AT&T

## BLOCK ELEMENTS
### HEADERS
Atx-style headers use 1-6 hash characters at the start of the line, corresponding to header levels 1-6. For example:
# This is an H1

## This is an H2

###### This is an H6

### BLOCKQUOTES
It looks best if you hard wrap the text and put a > before every line:
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

Markdown allows you to be lazy and only put the > before the first line of a hard-wrapped paragraph:

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.

Blockquotes can be nested (i.e. a blockquote-in-a-blockquote) by adding additional levels of >:
> ## This is a header.
> 
> 1.   This is the first list item.
> 2.   This is the second list item.
> 
> Here's some example code:
> 
>     return shell_exec("echo $input | $markdown_script");
## LISTS
Markdown supports ordered (numbered) and unordered (bulleted) lists.

Unordered lists use asterisks, pluses, and hyphens — interchangably — as list markers:
*   Red
*   Green
*   Blue

is equivalent to:
- red
- green
- blue
and:
+ red
+ green
+ blue

Ordered lists use numbers followed by periods:
1.  Bird
2.  McHale
3.  Parish
To put a blockquote within a list item, the blockquote’s > delimiters need to be indented:
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.
    
To put a code block within a list item, the code block needs to be indented twice — 8 spaces or two tabs:
*   A list item with a code block:

        <code goes here>
It’s worth noting that it’s possible to trigger an ordered list by accident, by writing something like this:  

  1986. What a great season.
In other words, a number-period-space sequence at the beginning of a line. To avoid this, you can 
backslash-escape the period:
  
  1986\. What a great season.
  
## CODE BLOCKS
To produce a code block in Markdown, simply indent every line of the block by at least 4 spaces or 1 tab.
For example, given this input:
This is a normal paragraph:

    This is a code block.
    
One level of indentation — 4 spaces or 1 tab — is removed from each line of the code block. For example, this:

Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
    
## HORIZONTAL RULES

* * *
hello word
***

*****

- - -

---------------------------------------

# SPAN ELEMENTS
## LINKS
To create an inline link, use a set of regular parentheses immediately after the link text’s closing 
square bracket. Inside the parentheses, put the URL where you want the link to point, along with an 
optional title for the link, surrounded in quotes. For example:

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

If you’re referring to a local resource on the same server, you can use relative paths:
See my [About](/about/) page for details.   
Reference-style links use a second set of square brackets, inside which you place a label of your
choosing to identify the link:

This is [an example][id] reference-style link.
Then, anywhere in the document, you define your link label like this, on a line by itself:
[id]: http://example.com/  "Optional Title Here"

## EMPHASIS

Markdown treats asterisks (*) and underscores (_) as indicators of emphasis. Text wrapped with one * or _ will
be wrapped with an HTML \<em> tag; double *’s or _’s will be wrapped with an HTML \<strong> tag. E.g., this input:

*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

Emphasis can be used in the middle of a word:

un**frigging**believable

To produce a literal asterisk or underscore at a position where it would otherwise be used as an 
emphasis delimiter, you can backslash escape it:

\*this text is surrounded by literal asterisks\*

## CODE

To indicate a span of code, wrap it with backtick quotes (`). Unlike a pre-formatted code block, 
a code span indicates code within a normal paragraph. For example:

Use the `printf()` function.

To include a literal backtick character within a code span, you can use multiple backticks as the 
opening and closing delimiters:

``There is a literal backtick (`) here.``


The backtick delimiters surrounding a code span may include spaces — one after the opening, 
one before the closing. This allows you to place literal backtick characters at the beginning or end of a code span:

A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``

With a code span, ampersands and angle brackets are encoded as HTML entities automatically, 
which makes it easy to include example HTML tags. Markdown will turn this:

Please don't use any `<blink>` tags.


