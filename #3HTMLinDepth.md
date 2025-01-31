# Learning HTML

- HTML5 is made of up

  - Core spec
    - markup changes
    - audio/video related changes
    - microdata
    - API changes (DOM, Canvas, and others)
  - Related Specs
    - Web Workers
    - Web Storage
    - Web SQL DB
    - Web Sockets
    - Geolocation

- What Browsers Do

  - browser collapse and ignore space and returns in HTML documents
  - browsers ignore unknown tags
  - browsers ignore unknown attributes
  - browsers let just about anything render

- Doctypes Redux
  - DOCTYPE indicates dialect of HTML used in a document
    - traditionally SGML based and pointed to a DTD file in some cases
    - later XML based for XHTML
    - moder non-descriptive as everything is just "HTML"
  - Doctype is useful for
    - validation
      triggering the rendering mode

## Global Attributes and Applications

- Global Attributes
  - New attributes for all tags well beyond the core (id, class, style, title) and language (lang, dir) attributes from HTML 4

## Core Attributes

- Core Attributes

  - There are four attributes that are core to nearly every HTML tag
    1. id - a unique name for the element for scripting, styling, and linking
    2. class - a space separated list of group names for the element for scripting and styling
    3. style - css properties to style the element
    4. title - advisory text that describes the element or its purpose

- id

  - id attribute is used to set a unique name/identifier for an element
    - be careful to use a reasonable name that could be referenced in CSS, within URLs, and in JavaScript

- class

  - class attribute is used to set a group name/identifier for an element. This name is primarily used for CSS to effect a look on set of HTML elements but may be used via JavaScript

- title

  - title attribute is used to set advisory text for an element
  - generally a user agent will display advisory information as a tooltip for the element

- title usage

  - title attribute may not be useful for touch users, keyboard focused usres, users with motor skills issues, etc

- style
  - style attribute is used to set CSS properties inline on a tag. This properties will generally override other CSS values set document wide or externally

## Accessibility (A11y) Attributes

- autofocus

  - indicates that the given element should have focus when the page has finished loading
    - focus typically occurs by placing the cursor in that element's text-box or by tab selecting the element
    - can only be used on `<button>`, `<input>`, `<select>`, and `<textarea>` elements
    - no more than one element in a document may have this element
    - cannot be used on hidden elements

- accesskey
  - all elements now have the possibility of an accesskey (usually alt+key specified)
- tabindex
  - traditionally only on form fields or some interactive elements (links)
  - now all elements are part of tab order from low to high
    - commonly -1 to put out of tabbing order

## Internationalization (i18n) Attributes

- language - dir and lang

  - improve internationalization HTML4 added lang and dir attributes to most tags to indicate the language and text flow direction for content

- translate
  - a newer global attribute translate would be used in conditions where automatic translation/localization is used to avoid items being converted

## Interactivity Attributes

- contenteditable

  - when set to true allows simple editing of content in browser
  - does not determine how the change is retained

- contextmenu

  - defines the DOM id of the `<menu>` to serve as a context menu for the element this attribute is defined for
  - so far no implementations however, likely could be simulated with oncontextmenu event in JavaScript

- draggable attribute

  - attribute is set to true or false to indicate if an element is draggable or not

- hidden attribute

  - inidicates if an element is no longer relevant and should be hidden or not
    - likely this is to address the misuse of the CSS rule (display : none)

- spellcheck attribute
  - this attribute can be set to true and false to allow for controlling checking the spelling of content
    - dominantly used on form fields

## Event Attributes

- interactivity - event attributes
  - mouse clicking
    - onclick, ondblclick
  - mouse buton movement
    - onmousedown, onmouseup
  - mouse movement
    - onmouseover, onmousemove, onmouseout
  - key presses
    - onkeydown, onkeyup, onkeypress

## Data Attributes

- data-x attributes

  - allows for user-defined meta data
    - reduces name collision problems
    - removes overloading of class attributes or invention of non-standard attributes

- data-x versus class

  - many devs overload the class attribute using it to signal the interactive nature of an element, hold element/component state, or even hold data

- microdata
  - microdata exists to offer scripts and machines data for the webpage that is a bit easier for them to parse so they don't have to dig around the page content for it
    - all of the microdata attributes start with item
  - itemscope neotes that the HTML contained inside the given block is an item
    - itemprop lets you add a key/value pair to the itemscope object
    - itemid lets you add a unique easily identifiable to the element with the itemscope to easily reference that item later
    - itemref lets you include other itemscopes in your itemscope
    - itemtype lets you link a schema / set of vocab that your microdata will be following

## Head Elements

- `<title>`

  - most important head element
    - for bookmarking
    - for robots

- meta information

  - meta information is simply information about information
    - typically used in searching and categorization of information
    - think about ideas like subject, author, ISBN, page count, etc.
  - on the web meta data is primarily indicated with the `<meta>` tag which can indicate arbitrary data
  - the `<meta>` tag is mainly used for the following:
    - author and description indications for search engines
    - HTTP control information for caching, filtering, language or charset indication, and other delivery related services
    - responsive design

- `<meta>` syntax

  - name attribute is used to specify the name of the meta data and the content attribute the associated information
    - the choice ofo th ename and the content is actually somewhat arbitrary

- link relationships

  - linking can have meaning as specified by the `<link>` tag
    - you can specify different stylesheets for different media types using the media attribute

- `<base>`

  - a `<base>` tag is used to set a reference or base URL so other links in the page assume this prefix

- `<style>`

  - `<style>` tags are often found in the document head and contain styles for the page
  - the media attribute can be used to set style by output

- `<script>`
  - putting `<script>` in a document head ensures it is loaded before the page unless directed otherwise by the (defer) attribute

## Body Elements

- `<body>`
  - the `<body>` tag is used to contain the content of the document
    - only one `<body>` per document

## Sectioning Elements

- `<main>`

  - semantic element that should be used only once in the `<body>` and should not be contained inside of structures like `<header>`, `<footer>`, `<article>`, `<aside>`, or `<nav>`

- `<section>` details

  - sections can contain sub-sections and even `<header>` and `<footer>` tags

- headings

  - `<h1>`, `<h2>`, `<h3>`, etc
  - headings are block tags

- `<hgroup>`

  - represents a multi-level heading for a section of a document
    - groups a set of `<h#>` elements as one heading
  - typically used to create subheadings

- `<article>`

- `<aside>`

- `<p>`

  - the `<p>` element indicates a paragraph of text
    - the paragraph element has semantic meaning, though visually given that it is a block element most browsers will create a blank line between consecutive non-empty paragraphs
    - you may see some developers insert simulate returns by inserting the character entity for a space in a paragraph

- `<br>`

  - `<br>` are empty elements that indicate line breaks

- `<hr>`

  - `<hr>` signifies a thematic break between paragraph-level elements - this is usually visually rendered by default with a horizontal line

- `<nav>`

- `<search>`

  - a recent semantic addition to HTMl is a semantic element for indicating the elements are used as site/app search

- divisions

  - the `<div>` tag is a generic block tag used to create a division or "section" in a document

- spans

  - like `<div>`, the `<span>` tag is generic in that it has no predefined visual rendering
  - `<span>` is an inline tag rather than a block tag so it is used to effect smaller regions of content

- quotations

  - large quotations are set off with `<blockquote>` and small inline quotations with the `<q>` tag

- preformatted text

  - the `<pre>` tag is used to indicated that something is preformatted, letting the browser know not to apply standard HTML rules of whitespace and formatting on it

- `<figure>` and `<figcaption>`

- address
  - an `<address>` tag is used to set the address of the document's maintainer
    - while it is a logical tag, it is usually rendered in the same font style as a paragraph tag except italicized
  - generally should only be one of these per document and at the end of the document

## Lists
