---
toc: true
layout: post
title: "Markdown basics"
description: The basics of markdown.
categories: [markdown]
---

 Here are some notes about basic syntax of markdown.
 Built with <i class="fas fa-heart"></i> from Grav and Hugo

# Headings

Headings are with number sign (\#) in front of a word or a phrase. The number of # signs indicate the level of the headings. For example, first-level heading is using '\#' and second level heading is using '\#\#'.
Remember to add space between "\#" and your word or phrase.

Here is the example:

### Header three

#### Header four

##### Header five

###### Header six


# Emphasis
In general, we need to add emphasis to the content by using bold or italic texts.

## Bold
Bold type is created by add two asterisk (\*\*) around the letter without space.eg:

> **I am bold text.**

## Italic
Italic type is created by add one asterisk(\*) or underscore(\_) around the letter without space.Eg:
> Use\* : *I am italic text.*  

or

>use \_ : _I am italic text as well._

## Bold and Italic
This type is created by adding three asterisk (\*\*\*) around the letters without space. Eg:
> ***I am both bold and italic texts.***

# Blockquotes
Blockquote is created by adding a \> in front of a sentence or paragraph.

> Here shows the rendered output of a blocquoted texts.
  > Here is a nested blockquoted texts.

# URLs

## write down links

When writing a link, put angle brackets around the link. (\< url \>)

Here is a link to this blog: <https://yliu566.github.io/>

## super link to a website
use format" \[Name_of_the_webste\](website link address)". Eg:
> Please enjoy reading [my blog](https://yliu566.github.io/)

# Lists

## Ordered list
Ordered list is created by add numbers with a period to each line items. The following is an example.

1. First item
2. Second item
3. Third item
4. Fourth item
    1. subitem 1
    2. subitem 2

## Unordered list
Unordered list is created by add dash (\-), asterisk (\*) or plus sign (\+) in front each items.

- First item
- Second item
- Third item
- Fourth item
  - subitem 1
  - subitem 2

# Tables

### Table 1

| Entry         | Item   |                                          |
| --------      | ------ | ---------------------------------------- |
| [item1](#)    | 1111   | Description of the item in the list      |
| [item2](#)    | 2222   | Description of the item in the list      |
| [item3](#)    | 3333   | Description of the item in the list      |

### Table 2

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|-----------------------------|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=============================|
| Foot1   | Foot2   | Foot3   |


# Adding images

how to add images?



## Buttons

Make any link standout more when applying the `.btn` class.

## Notices

**Watch out!** You can also add notices by appending `{: .notice}` to a paragraph.
{: .notice}

eg:
> You can also add notices by appending{.notice}

## HTML Tags

### Address Tag

<address>
  1 Infinite Loop<br /> Cupertino, CA 95014<br /> United States
</address>

### Anchor Tag (aka. Link)

This is an example of a [link](http://github.com "Github").

### Abbreviation Tag

The abbreviation CSS stands for "Cascading Style Sheets".

*[CSS]: Cascading Style Sheets

### Cite Tag

"Code is poetry." ---<cite>Automattic</cite>

### Code Tag

You will learn later on in these tests that `word-wrap: break-word;` will be your best friend.

### Strike Tag

This tag will let you <strike>strikeout text</strike>.

### Emphasize Tag

The emphasize tag should _italicize_ text.

### Insert Tag

This tag should denote <ins>inserted</ins> text.

### Keyboard Tag

This scarcely known tag emulates <kbd>keyboard text</kbd>, which is usually styled like the `<code>` tag.

### Preformatted Tag

This tag styles large blocks of code.

<pre>
.post-title {
  margin: 0 0 5px;
  font-weight: bold;
  font-size: 38px;
  line-height: 1.2;
  and here's a line of some really, really, really, really long text, just to see how the PRE tag handles it and to find out how it overflows;
}
</pre>

### Quote Tag

<q>Developers, developers, developers&#8230;</q> &#8211;Steve Ballmer

### Strong Tag

This tag shows **bold text**.

### Subscript Tag

Getting our science styling on with H<sub>2</sub>O, which should push the "2" down.

### Superscript Tag

Still sticking with science and Isaac Newton's E = MC<sup>2</sup>, which should lift the 2 up.

### Variable Tag

This allows you to denote <var>variables</var>.
