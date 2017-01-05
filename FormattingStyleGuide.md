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

## Version history
- Markdown document should include version history table. 
- Version history table is describing what changes have been made to document.
- Newest (latest) change comment is at the bottom of table (oldest is on the top of table).
- Version history table is positioned after the document name and ID fields and before the table of contents.

## Table of contents
- Provide table of contents for longer documents.
- Use links in the table of contents. Use [GitHub heading anchors](https://gist.github.com/asabaylus/3071099). For example,
```
  [Table of contents](StyleManual.md#table-of-contents) 
```
links to this section.

## Licence
- Use Creative Commons Attribution-ShareAlike 3.0 Unported License.
- Create separate chapter for licence and add the following licence text to this chapter (remove quotation marks):
```
  "This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/ "
```
- Licence chapter must be the very first chapter in markdown document (first one after the table of contents).

## Linking
- Use [relative linking](https://github.com/blog/1395-relative-links-in-markup-files) to link to image files and other documents in the same repository.

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
