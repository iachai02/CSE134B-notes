# Introduction to Markup

- Introduction to Markup

  - markup is information added to a text document to indicate the structure and potentially format of that information
  - thus a marked-up document contains:
    - data
    - information about that data (markup)
  - markup is all around us even in the day of WYSIWYG, it just tends to be invisible to us within the document format of the files we often work on

- Definitions

  - A markup language is a formalized way of providing markup and must specify:
    - what markup is allowed and where
    - what markup is required
    - how markup is distinguished from text
    - what markup means
  - markup languages often come in two camps:
    1. presentational - how something looks
    2. semantic - what something means

- SGML Structure

  - Under SGML (and later XML) documents, we have an inverted tree structure with a root element containing all others
  - SGML provided three basic markup structures:
    - Elements
      - `p`
    - Attributes to modify elements
      - `align="center"`
    - Entities for representing special characters
      - `&copy;`

- Tags and Elements

  - Tags are the items actually embedded the document
    - tags contain names of element types
      - `<p>`
    - they are positioned to indicate beginning and end of occurrences of elements
      - `<p>   <p>`
    - they are distinguished from data by delimiters
      - `< > and </ >`

- Defining the language

  - you might wonder how I came up with the tags. In the case of SGML you declare the structure of a particular type of document including allowed elemetns, attributes in entities in a file called a Document Type Definition or DTD
  - A DTD defines one particular type of document
  - From an object oriented point of view a DTD defines a "class" while a document would be an instance of that class as it conforms to the DTD

- The Idea of Validation
  - Given a document we could check to see if it conforms to the previous DTD or is "valid"
  - this checking of document instance against a DTD is a process known as validation
  - validation is well known in SGML and XML, but not so well in HTML which seems obvious given HTML's history

## HTML

- HTML and XHTML

  - HTML and XHTML are the not-so-behind the scenes markup languages that are used to tell web browsers ('user agents') hot to structure and, some may say display web pages
    - HTML - Hypertext Markup Language
    - XHTML - Extensible Hypertext markup language

- Markup Quickstart

  - HTML document is a structured text document composed of elements, entitites and text fragments
  - markup elements are made up of a start tag (e.g. `<strong>`) and might include an end tag that contains a closing slash character (e.g. `</strong>`)
  - the browser applies the meaning of the element to the enclosed content
  - under traditional HTML some elements are empty -- they enclose no content and thus they have no close tage (e.g. `<hr>`)
  - the start tag of an HTML element may contain attributes that modify the meaning of the tag
  - in traditional HTML some attributes affected a tag simply by their existence `<hr noshade>`
  - under XHTML attribute values are always required so `<hr noshade="noshade" /> would be the correct XHTML syntax

- Markup Quickstart - Content Model

  - The HTML specification indicates that some elements are only to used under certain conditions
    - example: list items `<li>` are only supposed to occur within ordered list `<ol>` and unordered lists `<ul>`
  - breaking the content model is quite common through and elements may be inserted by the user agent to mitigate the mistakes in most cases

- Markup Quickstart - Entities
  - characters that are special like <, >, &, etc. (these are part of the HTML syntax itself should be escaped)

## Learning HTML Formally

- Document Types
  - All valid documents begin with a `<!DOCTYPE>` declaration
    - in the basic sense it identifies the markup "dialect" used in a document by referencing an external DTD
    - A DTD defines the actual elements, attributes, and element relationships that are valid in documents
    - HTML 5 and beyond has a bit of a different attitude about doctypes, but we always must include one

## Learning HTML Pracitically

- Presentational vs. semantic markup

  - traditionally HTML has struggled as a markup language because it supported both presentation elements (`<font>`, `<b>`, `<big>`, `<small>`) as well as more semantic elements (`<em>`, `<p>`, `<div>`, `<blockquote>`)

- Curing `<div>`-itis

  - some semantic alternatives to `<div>`
    - when making a header, use the `<header>` element
    - when making the navigation bar, use the `<nav>` element
    - when dividing the content on a page into sections, use the `<section>` element

- Curing Class-itis

  1. use built-in elements `<button>` not `<div class="button">`
  2. Rely on rules for built-ins and custom elements directly override groups with class, and do thing to specific instances via id
  3. practice separating concerns with semantic markup - presentational classes with clear indications of look, aren't that

- `<head>`

  - The head of a document delimited by `<head>` includes supplementary information about the document including document title, scripts, styles, meta information, etc.

- `<body>`

  - body contains the content of the page
  - generally it will be enclosed in larger block structures which in term enclose smaller structures

- Within the `<body>`

  - within the body you have block-level elements which define structural content blocks like paragraphs `<p>` or headings `<h1>`
  - within block structures we see inline elements like bold `<b>`, emphasis `<em>` and so on

- Block Elements

  - what are they?
    - elements that horizontally span their entire container and have a new line character before and after them
    - they are only as tall as the content within them
  - where are they used?
    - typically are used to directly hold large amounts of content, and often act as parent containers
  - examples
    - `<p>`, `<article>`, `<details>`, `<div>`, `<figure>`

- Inline Elements

  - What are they?
    - Elements that (by default) are only as wide and tall as content within them
    - They do not have any new line characters since they are used inside of lines
  - Where are they used?
    - They typically are used within blocks of content, typically to add attributes to a specific bit of text for stylistic or functional purposes
  - examples
    - `<a>`, `<em>`, `<q>`, `<time>`, `<span>`, `<strong>`

- Inline-Block Elements

  - What are they?
    - CSS specific designation as no element is inline-block by default in HTML
    - In CSS, you can modify the height, width, padding, and margins of block level elements but not of inline level elements
    - Setting an element to be inline-block allows you to modify those properties on the element while still treating it as if it were inline
  - Where are they used?
    - they have a variety of purposes, one such example may be in styling the links of a horizontal navigation bar

- Within the `<body>`

  - Further structures like lists `<ul>`, images `<img>`, scripts `<script>` are also found in the `<body>` but may fall outside the hierarchy you might expect
  - the concept of tags enclosing only certain types of other tags is dubbed the content model

- Void Elements

  - do not enclose any content

- Escapable Raw Text Elements

  - These elements escape tags, but not character entities

- Raw Text Elements

  - elements contain other technologies (CSS or JavaScript) and should not be interpreted by HTML parsing

- Template Element

  - element is used to hold insert content. Tag is commonly used to define views to show with JavaScript or create custom elements. Content within templates will not show up on parse

- Foreign Elements

  - elements are from other "HTML" friendly languages notably MathML and SVG

- Comment Usage - masking
  - mask inline technology from downgrade user-agents so they do not treat it as page content
