# Markdown Style Guide

The Rocket.Chat documentation utilizes the [Markdown Markup Language](https://en.wikipedia.org/wiki/Markdown) (a "Cheatsheet" is available [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)). Markdown can be composed in a variety of styles, but this document outlines the standard formatting guide for creating Rocket.Chat documentation. Please note, we are presently implementing a markdown [linter](https://github.com/markdownlint/markdownlint) on incoming Pull Requests. Therefore, it's advisable to ensure your commits pass the linting test prior to submitting a Pull Request. Each rule listed here includes its respective code, so if the linter flags an issue, you can refer back to this guide to identify the broken rule.

| Rules                                                                                    | Description                                                                                                                                                                                  | Wrong                                                                                                                                                                             | Correct                                                                                                                  |
| ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **MD001 - Header levels should only increment by one level at a time**                   | Headers should not be skipped, but instead incremented one by one.                                                                                                                           | <pre><code># Header 1

### Header 3

We skipped out a 2nd level header in this document
</code></pre>                                                                             | <pre><code># Header 1

## Header 2

### Header 3

#### Header 4

## Another Header 2

### Another Header 3
</code></pre> |
| **MD002 - First header should be a top-level header**                                    | The first header of the document should be a top-level header (H1).                                                                                                                          | <pre><code>## This isn't a H1 header

### Another header
</code></pre>                                                                                                            | <pre><code># Start with a H1 header

## Then use a H2 for subsections
</code></pre>                                      |
| **MD003 - Header style**                                                                 | The header style used on documents should be `atx`.                                                                                                                                          | <pre><code>Setext style H1
===============

Setext style H2
---------------
</code></pre>                                                                                         | <pre><code># ATX style H1

## ATX style H2
</code></pre>                                                                 |
| **MD004 - Unordered list style**                                                         | Lists should be created using asterisks.                                                                                                                                                     | <pre><code>* Item 1
+ Item 2
- Item 3
</code></pre>                                                                                                                               | <pre><code>* Item 1
* Item 2
* Item 3
</code></pre>                                                                      |
| **MD005 - No inconsistent indentation for list items at the same level**                 | Lists should maintain consistent indentation. Typically, any violation of this rule is due to a typographical error.                                                                         | <pre><code>* Item 1
      * Nested Item 1
      * Nested Item 2
     * A misaligned item
</code></pre>                                                                            | <pre><code>* Item 1
    * Nested Item 1
    * Nested Item 2
    * Nested Item 3 --->Aligned
</code></pre>                |
| **MD006 - Start bulleted lists at the beginning of the line**                            | Lists with bullet points should commence at the start of the line                                                                                                                            | <pre><code>Some text

  * List item
  * List item
</code></pre>                                                                                                                   | <pre><code>Some text

* List item
* List item
</code></pre>                                                              |
| **MD007 - Unordered list indentation**                                                   | List items should be indented using 4 spaces.                                                                                                                                                | <pre><code>* List item
    * Nested list item indented by 3 spaces
</code></pre>                                                                                                  | <pre><code>* List item
    * Nested list item indented by 4 spaces
</code></pre>                                         |
| **MD009 - No trailing spaces**                                                           | There should be no trailing spaces at the end of lines. To rectify this, locate the flagged line and eliminate any spaces trailing at its end.                                               |                                                                                                                                                                                   |                                                                                                                          |
| **MD010 - No hard tabs**                                                                 | Indentation should be achieved using spaces, not hard tabs.                                                                                                                                  |                                                                                                                                                                                   |                                                                                                                          |
| **MD011 - No reversed link syntax**                                                      | When creating links you should use the `[]` surrounding the text and `()` surrounding the link.                                                                                              | <pre><code>(Incorrect link syntax)[http://www.example.com/]
</code></pre>                                                                                                         | <pre><code>[Correct link syntax](http://www.example.com/)
</code></pre>                                                  |
| **MD012 - No multiple consecutive blank lines**                                          | The document should not contain more than one consecutive blank line.                                                                                                                        | <pre><code>Some text here


Some more text here
</code></pre>                                                                                                                     | <pre><code>Some text here

Some more text here
</code></pre>                                                             |
| **MD018 - Use space after hash on atx style header**                                     | <p></p><p>There should be a space after the hashes on atx style headers.</p>                                                                                                                 | <pre><code>#Header 1

##Header 2
</code></pre>                                                                                                                                    | <pre><code># Header 1

## Header 2
</code></pre>                                                                         |
| <p><strong>MD019 - No multiple spaces after hash on atx style header</strong></p><p></p> | In atx style headers, there should not be more than one space following the hash symbol.                                                                                                     | <pre><code>#  Header 1

##  Header 2
</code></pre>                                                                                                                                | <pre><code># Header 1

## Header 2
</code></pre>                                                                         |
| **MD022 - Headers should be surrounded by blank lines**                                  | Every header should be preceded and followed by a blank line, unless the header is positioned at the start or end of the document.                                                           | <pre><code># Header 1
Some text

Some more text
## Header 2
</code></pre>                                                                                                         | <pre><code># Header 1

Some text

Some more text

## Header 2
</code></pre>                                              |
| **MD023 - Headers must start at the beginning of the line**                              |                                                                                                                                                                                              | <pre><code>Some text

    # Indented header
</code></pre>                                                                                                                         | <pre><code>Some text

# Header
</code></pre>                                                                             |
| **MD025 - No multiple top-level headers in the same document**                           | A document should contain only one top-level header (h1)                                                                                                                                     | <pre><code># Top level header

# Another top level header
</code></pre>                                                                                                           | <pre><code># Title

## Header

## Another header
</code></pre>                                                           |
| **MD027 - No multiple spaces after the blockquote symbol**                               | Blockquote should not have more than one space after the blockquote symbol ( `>` ).                                                                                                          | <pre><code>>  This is a block quote with bad indentation
>  there should only be one.
</code></pre>                                                                               | <pre><code>> This is a block quote with good indentation
> there should only be one.
</code></pre>                       |
| **MD028 - No blank line inside blockquote**                                              | A blockquote should not contain a blank line within it. However, if the lines are intended to be part of the same quote, then prepend the blockquote symbol to the start of the blank line.  | <pre><code>> This is a blockquote
> which is immediately followed by

> this blockquote. Unfortunately
> In some parsers, these are treated as the same blockquote.
</code></pre> | <pre><code>> This is a blockquote.

And Jimmy also said:

> This too is a blockquote.
</code></pre>                      |
| **MD029 - Ordered list item prefix**                                                     | Ordered lists should be ordered by a prefix that increases in numerical order.                                                                                                               | <pre><code>1. Do this.
1. Do that.
1. Done.
</code></pre>                                                                                                                         | <pre><code>1. Do this.
2. Do that.
3. Done.
</code></pre>                                                                |
| **MD030 - Space after list markers**                                                     | There should be only one space after a list marker.                                                                                                                                          | <pre><code>*Foo
*Bar
*Baz

1.  Foo
1.  Bar
1.  Baz
</code></pre>                                                                                                                  | <pre><code>* Foo
* Bar
* Baz

1. Foo
1. Bar
1. Baz
</code></pre>                                                         |
| **MD031 - Fenced code blocks should be surrounded by blank lines**                       |                                                                                                                                                                                              | <p></p><p></p>                                                                                                                                                                    |                                                                                                                          |
| **MD032 - Lists should be surrounded by blank lines**                                    |                                                                                                                                                                                              | <pre><code>Some text
* Some
* List

1. Some
2. List
Some text
</code></pre>                                                                                                       | <pre><code>Some text

* Some
* List

1. Some
2. List

Some text
</code></pre>                                            |
| **MD034 - No bare URLs**                                                                 | Bare URLs should not be present in the document; instead, enclose the links within angle brackets (< >).                                                                                     | <pre><code>For more information, see http://www.example.com/.
</code></pre>                                                                                                       | <pre data-overflow="wrap"><code>For more information, see &#x3C;http://www.example.com/>.
</code></pre>                  |
| **MD035 - Horizontal rule style**                                                        | Horizontal rules should be created using three slashes (`---`).                                                                                                                              | <pre><code>***

* * *

****
</code></pre>                                                                                                                                         | <pre><code>---
</code></pre>                                                                                             |
| **MD037 - No spaces inside emphasis markers**                                            | Spaces should not be present within emphasis markers (such as bold or italic).                                                                                                               | <pre><code>Here is some ** bold ** text.

Here is some _ italic _ text.
</code></pre>                                                                                             | <pre><code>Here is some **bold** text.

Here is some _italic_ text.
</code></pre>                                        |
| **MD038 - No spaces inside code span elements**                                          | Spaces should not be included within code span elements.                                                                                                                                     | <pre><code>` some text `

`some text `

` some text`
</code></pre>                                                                                                                | <pre><code>`some text`
</code></pre>                                                                                     |
| **MD039 - No spaces inside the link text**                                               |                                                                                                                                                                                              | <pre><code>[ a link ](http://www.example.com/)
</code></pre>                                                                                                                      | <pre><code>[a link](http://www.example.com/)
</code></pre>                                                               |
| **MD046 - Code block style**                                                             | Code blocks should be fenced.                                                                                                                                                                | <pre><code>  codeblock using indentation.
</code></pre>                                                                                                                           | <pre><code>```
codeblock without indentation.
```
</code></pre>                                                          |

{% hint style="info" %}
For a comprehensive guide on contributing to Rocket.Chat documentation, visit [.](./ "mention")and [repository-template.md](repository-template.md "mention")
{% endhint %}
