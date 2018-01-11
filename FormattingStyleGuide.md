# Formatting & Style Guide

## Scope and purpose
This document provides formatting and style conventions for publishing documents in __GitHub__ in __Markdown__ format. Some advice on document conversion and how to meet more sophisticated publishing needs is offered.

## General
- Use [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
- Example document following this guide: [ExampleMarkdownDocument.md](ExampleMarkdownDocument.md).
- Documents must not define their own terms or abbreviations but rather use reference to X-Road terms document: [Terms of X-Road](https://github.com/ria-ee/X-Road/blob/develop/doc/terms_x-road_docs.md)
    - Add any new/missing term and abbreviation to X-Road terms document.

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
- Use links in the table of contents. Use [GitHub heading anchors](https://gist.github.com/asabaylus/3071099).
  For example the following code links to this section:

  ```
  [Table of contents](#table-of-contents) 
  ```
- Table of contents can be generated using a appropriate tool, for example, https://www.npmjs.com/package/markdown-toc or vim-markdown-toc.

## License
- Use Creative Commons Attribution-ShareAlike 3.0 Unported License.
- Create separate chapter for license and add the following license text to this chapter:

  ```
  This document is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License.
  To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/
  ```

- License chapter must be the very first chapter in markdown document (first one after the table of contents).

## Linking
- Use [relative linking](https://github.com/blog/1395-relative-links-in-markup-files) to link to image files and other documents in the same repository.
- Use anchors to create references:

  ```
  <a id="Ref_RFC2119"></a>\[RFC2119\] Key words for use in RFCs to Indicate Requirement Levels,
  Internet Engineering Task Force, 1997.
  ```

- When linking or referencing X-Road documents use document abbreviation:

  ```
  [\[ARC-G\] X-Road Architecture](Architecture/arc-g_x-road_arhitecture.md)  
  ```

## Code
- Use backticks to mark inline code, URLs a.o. constant values.
- Use GitHub Markdown code fencing to format blocks of code.

## Tables
- Use GitHub Flavored Markdown features.

## Conversion
- Use programmer's editor (e.g. [Sublime Text](https://www.sublimetext.com/)), or just Notepad to convert documents from Word, Confluence, PDF a.o. formats to Markdown.
- Specialized converter software (e.g. [Pandoc](http://pandoc.org/)) can be used, but will rarely justify the learning effort.

## Drawing tool
- Use draw.io to create drawings, flowcharts and pictures for X-Road documentation. Draw.io (https://www.draw.io/) is completely free online diagram editor. It can be also used in offline mode by going to the following URL into your web browser: https://www.draw.io/app or by using Chrome Application.
- Use PNG file format in documents and save the original source file as native XML. Both files must be committed into Github to "img" sub-folder of the document.

## For more sophisticated publishing
- For more sophisticated presentation needs, consider using [Hugo](https://gohugo.io/), [Jekyll](https://jekyllrb.com/) or some other website generation tool that accepts Markdown.

## References
[GitHub Mastering Markdown](https://guides.github.com/features/mastering-markdown/)

