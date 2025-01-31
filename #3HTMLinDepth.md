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
