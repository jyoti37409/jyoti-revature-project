# HTML CSS Study Guide

## Intro to HTML

### Overview of HTML
**Hypertext Markup Language** **HTML**, is the standard language used to create web pages. It defines the structure and layout of a web page using a series of elements like headings, paragraphs, images, and links. When combined with other languages like JavaScript and **CSS**, **HTML** helps create dynamic and interactive web pages. Web browsers have interpreters that convert **HTML** into content displayed on the screen. This markup language is quite forgiving, as browsers will attempt to fix any broken **HTML** to ensure it can still be interpreted. Webpages are structured using large blocks called **elements**, which consist of an opening tag, content, and a closing tag. These **elements** are manged through the use of the **Document Object Model (DOM)**

### HTML & the DOM
The **Document Object Model (DOM)** is a representation of an **HTML** document in memory. It is generated by the browser when a web page is rendered and can be manipulated by Web APIs to interact with the page as it is being viewed. The **DOM** acts as an interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document. While JavaScript is commonly used to manipulate the **DOM**, any language that can interact with Web APIs can be used

## HTML Foundation

### HTML Tags
**HTML** **tags** denote the start and end of an **element**. For example, to define a paragraph in **HTML**, you would write `<p></p>` in the **HTML** file. This line begins and ends with the same syntax, with the difference being the `/` added to the closing **tag**. The `/` tells the interpreter that the **element** is finished, so any **tag** with a `/` in front is referred to as a `closing tag`. The terms **tag** and **element** are often used interchangeably, which can be confusing. The **tag** determines the functionality and structure, while the entire block from start to finish is referred to as the **element**. For example, in the HTML **element** `<p>Hello World</p>`, `<p>` is the **opening tag**, "Hello World" is the enclosed text content, and `</p>` is the **closing tag**. The entire structure is called the **element**, but the look and feel are determined by the **tags** used

### Elements & Attributes
**Attributes** in **HTML** are key-value pairs used to set various properties of an element, and they are always included in the **opening tag**. These **attributes** serve different purposes, such as identification and functionality. For identification, **attributes** like `id` and `class` are commonly used. The `id` **attribute** assigns a unique identifier to an **element**, allowing it to be easily targeted by **CSS** or JavaScript. The `class` **attribute**, on the other hand, can be used to group multiple **elements** together, making it easier to apply styles or behaviors to them collectively. Functionality-related attributes include `href` for links, `src` for images, and `alt` for alternative text for images. The `href` **attribute** specifies the URL of the page the link goes to, while the `src` **attribute** defines the source of an image. The `alt` **attribute** provides alternative text for an image, which is displayed if the image cannot be loaded, and is also used by screen readers for accessibility. Other **attributes** can control the behavior of **elements**, such as `disabled` for form inputs, `checked` for checkboxes, and `readonly` for text fields

### Inline & Block Elements
**HTML elements** can be categorized into two main types: **inline and block elements**. Each type has unique characteristics that affect how they are displayed on a webpage. For example, the `<p>` and `<span>` elements illustrate these differences

A **block element**, like `<p>`, will stretch to take up the entire width of its container. It always begins on a new line and is followed by a new line. Examples of **block elements** include headings (`<h1>` to `<h6>`), paragraphs (`<p>`), divisions (`<div>`), ordered and unordered lists and their items (`<ol>`, `<ul>`, `<li>`), tables (`<table>`), and sections (`<section>`)

In contrast, an **inline element**, like `<span>`, will only take up as much space as its content requires. **Inline elements** do not start on a new line and can appear beside other **inline elements**. Examples of **inline elements** include links (`<a>`), spans (`<span>`), inputs (`<input>`), labels (`<label>`), and citations (`<cite>`)

### Common Tags
- `<p>`: Defines a paragraph of text
- `<button>`: Creates a clickable button
- `<input>`: Represents an input field where users can enter data
- `<table>`: Defines a table for organizing data in rows and columns
- `<a>`: Creates a hyperlink to another webpage or resource
- `<img>`: Embeds an image into the webpage
- `<select>`: Creates a drop-down list for selecting options
- `<div>`: Defines a division or section in an HTML document, often used for layout purposes
- `<span>`: Used to group inline elements for styling purposes without affecting the layout

## HTML Forms

### Form Elements & Attributes
**Forms** in **HTML** used to be essential for collecting user input and making web request; they are defined using the `<form>` tags. Commonly used **elements** within **forms** include `<input>` for various types of data entry (text, password, email, etc.), `<textarea>` for multi-line text input, `<select>` for drop-down lists, `<button>` for clickable actions, and `<label>` to provide descriptions for input fields

Unique **attributes** in **forms** help manage data and enhance functionality. The `action` **attribute** specifies the URL where the **form** data should be sent, while the `method` **attribute** defines the HTTP method (GET or POST) used to submit the **form**. The `name` **attribute** assigns a name to the **form** **element**, which is used to identify the data when it is submitted. These **attributes** alo can be used alongside others like `placeholder`, `required`, and `autocomplete`

### Input Elements & Input Types
**HTML** **inputs** allow users to provide various types of data to a webpage. The `type` **attribute** determines the kind of input that is allowed. For example, the "text" type allows text input, the "number" type allows numeric input, the "range" type provides a slider to select a value between a specified minimum and maximum, and the "file" type lets users upload files. Additionally, multiple **attributes** can be used in conjunction with the specified **input** type to further define what can and cannot be provided. For instance, the `min` and `max` **attributes** set the minimum and maximum values for the **input**, the `pattern` **attribute** specifies a regular expression that the **input** must match to be considered valid, and the `accept` **attribute** determines which file types are acceptable for upload

### Select & Multiselect
The **select** **element** in **HTML** allows users to choose one or more values from a pre-determined list. By default, this **element** is presented as a dropdown list, but it can be customized. For instance, the `multiple` **attribute** enables users to select more than one option, and **optgroups** can be used to organize **options** into groups. Keep in mind the text displayed for an **option** and the actual value, determined by the `value` **attribute**, are separate resources and can be different

### Submitting Forms
**HTML** **forms** enable the submission of data through POST and GET requests. GET requests append any **form** data as query parameters in the URL, while POST requests include the **form** data in the request body, formatted similarly to query parameters. Depending on the results of the request, **form** submissions will either refresh the current page or load a new page. However, this default behavior can be prevented by using JavaScript

### HTML5 Validation
There are two forms of client-side validation in **HTML**: **HTML** validation and JavaScript validation. **HTML** validation is faster but less customizable. It includes attributes such as `required`, which indicates that a field must be provided, `type`, which specifies the kind of input, and `pattern`, which specifies the regular expression that the input must match, among others. On the other hand, JavaScript validation takes longer to set up but offers greater flexibility, allowing for custom validation to be programmed according to specific needs

## CSS Foundation

### Overview of CSS
**Cascading Style Sheets** (**CSS**) provide styling information for web pages and other resources, such as XML, ensuring a consistent look and feel across different browsers. This is because **CSS** is standardized across web browsers, making it a reliable tool for web development. Additionally, there is a large pool of third-party resources available that can help quickly set up attractive styling for web pages

### Inline, Internal, & External Styling
Styling in **CSS** can be applied in several ways. **Inline styling** is provided directly within an **element** using the `style` **attribute**. **Internal styling** is defined within a **style element**, typically placed in the **header** of the page; placing it later in the page may cause a "flash of unstyled content." **External styling** is sourced from an external stylesheet, linked to the **HTML** document using the link **element** with the `href` and `rel` **attributes**. The order of style precedence is **inline**, **internal**, and then **external**

### CSS Properties
In **CSS**, **properties** are used to define specific types of styling for **HTML** **elements**. Each **property** is part of a key:value system, where the **property** name is the key and the desired styling is the value. For example, the `color` **property** changes the text color, the `text-align` **property** adjusts the alignment of text, and the `font-size` **property** modifies the size of the text. There are many other **properties** available, each designed to control different aspects of styling, such as `margins`, `padding`, `borders`, and `backgrounds`. Understanding and utilizing these **properties** allows for precise and flexible control over the appearance of web pages

### CSS Selectors
**CSS selectors** are used to determine how the browser applies styling to **elements**, in conjunction with the form of styling used (inline, internal, or external). Some common **selectors** include the **id selector**, which targets a specific element with a unique identifier; the **class selector**, which targets elements with a specific class **attribute**; the **tag selector**, which targets all **elements** of a particular type; and the **universal selector**, which targets all descendants from the **selector** starting point. Additionally, there are more complex **selectors** that allow for more precise targeting of specific **elements** or collections of **elements**. These complex **selectors** can include attribute selectors, pseudo-classes, and pseudo-elements, which provide greater flexibility and control over the styling of web pages

### CSS Variables
**CSS variables** are useful when multiple **selectors** share the same values, as they simplify both the initial application and future refactoring. To name a variable, use \-\- followed by the **variable name**, and set its value after a colon. This declaration looks similar to setting the value for a **CSS property**. The declaration must be done within a ruleset, so the **variables** will be valid within the chosen **selector**. For example, using `:root` makes the **variable** valid throughout the entire document

Alternatively, the `@property` rule can be used to declare the property name (still using --), followed by the **CSS** key/value pairs. **Variables** are accessed in **CSS** using the `var()` function, with the **variable** name passed as an argument. This approach allows for consistent and maintainable styling across a web page

### Flexbox
**CSS Flexbox** allows for organizing **elements** within a container in a uniform way. It provides capabilities such as vertically centering resources, resizing child **elements** to take up the same amount of space, and organizing columns of data. Key **CSS properties** for **Flexbox** include `display`, which enables the flex container capabilities; `flex-direction`, which sets the direction of the flex items; and `flex-wrap`, which controls whether the flex items should wrap onto multiple lines. The `flex-direction` and `flex-wrap` properties can be combined into the `flex-flow` shorthand **property**. Additionally, the `flex` **property** is used to define how a flex item will grow or shrink to fit the available space within the flex container. These **properties** work together to create a flexible and responsive layout for web pages

### Grid
**CSS Grid** allows for organizing **elements** within a container in a grid-like manner. It enables the creation of columns and rows, with specific values set for each cell in the grid. Key **CSS** properties for using Grid include `display`, which enables the grid container; `grid-template-column`s, which defines the column structure; and `grid-template-rows`, which defines the row structure. There are third-party tools available that can help set up grids for web pages, making it easier to create complex and responsive layouts

## Bootstrap
**Bootstrap** is a free-to-use third-party resource that provides templates for setting up common web page designs. It offers both free and premium options, allowing users to choose based on their specific needs. Bootstrap can be linked directly within a web page or downloaded for use in projects. This resource can significantly speed up the development process and ensure a professional and consistent design