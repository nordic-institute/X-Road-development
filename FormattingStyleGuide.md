# Formatting & Style Guide

## Scope and purpose
This document provides formatting and style conventions for publishing documents in __GitHub__ in __Markdown__ format. Some advice on document conversion and how to meet more sophisticated publishing needs is offered.

## General
- Use [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
- If the workflow prescribes the document to go into BitBucket repository first, then you may find [BitBucket Markdown Syntax Guide](https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html) useful.

## Title & headings
- Use # (h1) for document title.
- Use ## (h2) for top-level headings.
- Number the headings manually. There's no heading numbering support in Markdown.

## Table of contents
- Provide table of contents for longer documents.
- Use links in the table of contents. Use [GitHub heading anchors](https://gist.github.com/asabaylus/3071099). For example,
```
  [Table of contents](StyleManual.md#table-of-contents) 
```
links to this section.

## Linking
- Use [relative linking)(https://github.com/blog/1395-relative-links-in-markup-files) to link to image files and other documents in the same repository.

## Code
- Use backticks to mark inline code, URLs a.o. constant values.
- Use GitHub Markdown code fencing to format blocks of code.

## Tables
- Use GitHub Flavored Markdown features.

## Conversion
- Use programmer's editor (e.g. [Sublime Text](https://www.sublimetext.com/)), or just Notepad to convert documents from Word, Confluence, PDF a.o. formats to Markdown.
- Specialised converter software (e.g. [Pandoc](http://pandoc.org/)) can be used, but will rarely justify the learning effort.

## For more sophisticated publishing
- For more sophisticated presentation needs, consider using [Hugo](https://gohugo.io/), [Jekyll](https://jekyllrb.com/) or some other website generation tool that accepts Markdown.

## References
[GitHub Mastering Markdown](https://guides.github.com/features/mastering-markdown/)

[BitBucket Markdown Syntax Guide](https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html) 
