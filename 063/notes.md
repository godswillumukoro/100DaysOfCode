#### Date: 21-April-2021

Snippet on displaying images below:
`<img src="./illustrator.png" alt="Illustration of a Fox" width="450">`

## Lists

There are two there kinds of lists.

- Unordered Lists
  `<ul><li></li></ul>`
- Ordered Lists
  `<ol><li></li></ol>`
- Nested Lists
  `<ul><li>Shoes<ul><li>Nike Air Max</li></ul></li></ul>`

## Tables

`<table><thead><th>Email accounts</th></thead><tbody><tr><td>hey@gee.com</td></tr></tbody></table>`

## Forms & Input

Forms can displayed and sytled with HTML and CSS respectively. However, in order to process the form , you need to code that functionality with a programming language that works on the backend (eg. PHP, Javascript etc.)

`Code to be added here`

## Block and Inline Level Elements

Inline elements only takes up the full with of the element on that page. Allowing the next element take up the available space that is unused. `(eg. <a>, <span>)`

Block level elements span accross the full width of page and breaks the next element onto a new line. I there were an Inline element before it, it breaks itself onto a new line and does not take up the unused available space. `(eg. <p>, <div>)`

## Divs, Spans, Classes and IDs

Div is used in creating division (or sepration of affairs) in your code.
Spans are inline elements used to target specific text in code.

### Classes vs IDs

There is no functional difference between classes and IDs. It is good practice to have your ID naming convention be singular. Do you need to give multiple elements same style? Use classes. Would you have only one main header? Use IDs.

## HTML Entities

- Non breaking space: Gives an horizontal space `&nbsp;`

- Greater than: `&gt;`

- Less than: `&lt;`

- Copyright: `&copy;`

- Euro: `&euro;`

- Pound: `&pound;`

## HTML Semantic Tags

These are excellent for organizing your code since the name of the tags are quite descriptive. However, its main goal is for accessibility. Writing semantic HTML code helps people with hearing/vision disabilities understand what goes where. They are quite important to use and should be used in place of `<div>` which carries no semantic meaning.

Some examples:
`<header>`
`<footer>`
`<section>`
`<article>`
`<nav>`
