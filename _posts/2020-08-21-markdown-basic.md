---
title: "MARKDOWN"
date: 2020-08-21 10:45:00 -0400
categories: Markdown
---

# Markdown

## 1. What is Markdown

> **Markdown** is a [lightweight markup language](https://en.wikipedia.org/wiki/Lightweight_markup_language) with plain-text-formatting syntax.

The philosophy behind Markdown is that plain text documents should be readable without tags mussing everything up, but there should still be ways to add text modifiers like lists, bold, italics, etc. 

<u>Markup</u>: A markup language is a computer language that uses [tags](https://techterms.com/definition/tag) to define elements within a document. It is human-readable, meaning markup files contain standard words, rather than typical programming [syntax](https://techterms.com/definition/syntax). While several markup languages exist, the two most popular are [HTML](https://techterms.com/definition/html) and [XML](https://techterms.com/definition/xml).



## 2. How to Markdown

### 2.1 Header

> To create a heading, add number signs (`#`) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (`<h3>`), use three number signs (e.g., `### My Header`).

```markdown
# Title 1
## Title 2
### Title 3
```



# h1 tag

## h2 tag

### h3 tag

#### h4 tag

##### h5 tag

###### h6 tag



### 2.2 List

> **Unordered list**: add dashes (`-`), asterisks (`*`), or plus signs (`+`) in front of line items. Indent one or more items to create a nested list.

- bullet1
  - bullet2
    - bullet3

> **Ordered list**: add line items with numbers followed by periods. The numbers don’t have to be in numerical order, but the list should start with the number one.

1. list1
2. list2
   1. list2-1
   2. list2-2



### 2.3 Code Block

> Pre-formatted code blocks are used for writing about programming or markup source code. 

Inline: To denote a word or phrase as code, enclose it in backticks (`` `).

Block: To make a code block, put 3 backticks and enter.

```bash
$ git add.
$ git commit -m "first commit"
$ git push origin master
```



### 2.4 Image

> Markdown is a text format so naturally you can type in the Markdown representation of an image using `![A test image](image.png)` to put an image reference directly into the editor.

![markdown](https://www.mvps.net/docs/wp-content/uploads/2019/03/hello-world.png)



### 2.5 Link

> To create a link, enclose the link text in brackets (e.g., `[Duck Duck Go]`) and then follow it immediately with the URL in parentheses (e.g., `(https://duckduckgo.com)`).

[My LinkedIn Page](https://www.linkedin.com/in/jiwon-yu-96303210b/)

[My Github Note](https://letsgititdana.github.io/)



[Markdown Guideline Site](https://www.markdownguide.org/basic-syntax/#paragraphs-1)



### 2.6 Table

```markdown
| Column 1       | Column 2     | Column 3     |
| :------------- | :----------: | -----------: |
|  Cell Contents | More Stuff   | And Again    |
| You Can Also   | Put Pipes In | Like this \| |
```

| Column 1      |   Column 2   |     Column 3 |
| :------------ | :----------: | -----------: |
| Cell Contents |  More Stuff  |    And Again |
| You Can Also  | Put Pipes In | Like this \| |



### 2.7 etc.

##### Quotes

`>` and `enter`

> "Hello World!"

> def hello():
>
> > print("Hello World!")
> >
> > > hello()



##### Horizontal

`---`, `***`, `___` 

First Paragraph

---

Second Paragraph

---

Third Paragraph



##### Emphasis

`*` or `_` for Italic

`**` or `__` for Bold

`~~` for Cancel Line

Command Line Interface ***(CLI)***

Graphic User Interface ***(GUI)***

~~Cancel Line~~
