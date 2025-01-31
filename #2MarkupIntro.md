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
