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
