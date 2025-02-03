# Forms

## Forms

- Forms

  - HTML forms offer a native way to collect user input and add controls to your webpage without using JavaScript
  - surrounded by `<form>` tags

- `<form>` syntax

  - `<form>` element has two basic attributes which determine what to do when the form is being submitted
    - action - specifies the URL that will be called upon form submission (default is current URL)
    - method - the HTTP method that will be used to send the form data to the URL in the action attribute

- HTTP Methods

  - method attribute determines what HTTP method to use when sending the data. Some basic differences between the two options are
    - GET - Form information sent in the URL. Usually used when a response is expected based on the form parameters
    - POST - information sent in the HTTP body, generally more common for forms. Used usually to collect information, doesn't usually get a tailored response

- Form Structure Overview

  - Form controls come in many varities
    - text controls - text fields, password fiels, and large text boxes
    - checkboxes
    - radio buttons
    - pull down menus
    - scrolled lists
    - buttons - generic buttons, submit buttons, reset buttons

- Text Fields
  - Most form controls are defined using an `<input>` tag
  - name is a key attribute - generates the name in the name-value pair
    - be careful with id confusion
    - any `<input>` without this attribute will NOT be included int he submission
  - you should put labels on form controls
    - labels should have a for attribute with a value matching the id of their corresponding element
