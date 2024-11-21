# CSS Selectors and Rule Syntax Guide

## 1. CSS Rule Set Syntax

### Basic Structure:
```css
selector {
    property: value;
}
```

### Complete Rule Set:
```css
/* Single selector */
selector {
    property1: value1;
    property2: value2;
    property3: value3;
}

/* Multiple selectors */
selector1,
selector2,
selector3 {
    property: value;
}
```

## 2. Element Selectors

### Basic Element Selectors:
```css
/* Targeting specific HTML elements */
h1 {
    font-size: 24px;
}

p {
    line-height: 1.6;
}

div {
    padding: 20px;
}

/* Multiple elements */
h1, h2, h3 {
    font-family: Arial, sans-serif;
}
```

### Universal Selector:
```css
/* Targets all elements */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

## 3. Class Selectors

### Basic Class Selectors:
```css
/* Single class */
.button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
}

/* Multiple classes */
.button.primary {
    background-color: #007bff;
}

.button.secondary {
    background-color: #6c757d;
}
```

### Multiple Class Combinations:
```css
/* Elements with multiple classes */
.card.featured.large {
    width: 100%;
    border: 2px solid gold;
}

/* Element with specific class */
div.container {
    max-width: 1200px;
}

/* Multiple separate classes */
.btn-primary,
.btn-secondary,
.btn-success {
    border-radius: 4px;
}
```

## 4. ID Selectors

### Basic ID Selectors:
```css
/* Single ID */
#header {
    background-color: #333;
    color: white;
}

/* Element with specific ID */
nav#main-navigation {
    position: fixed;
    top: 0;
}
```

### Common ID Usage:
```css
/* Layout components */
#sidebar {
    width: 250px;
    float: left;
}

#main-content {
    margin-left: 270px;
}

#footer {
    clear: both;
    padding: 20px;
}
```

## 5. Pseudo-Classes

### Link Pseudo-classes:
```css
/* Unvisited links */
a:link {
    color: blue;
}

/* Visited links */
a:visited {
    color: purple;
}

/* Mouse over links */
a:hover {
    color: red;
    text-decoration: none;
}

/* Active/clicked links */
a:active {
    color: orange;
}
```

### State Pseudo-classes:
```css
/* Input focus */
input:focus {
    border-color: #007bff;
    outline: none;
}

/* Checked state */
input:checked + label {
    font-weight: bold;
}

/* Disabled elements */
button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}

/* Required fields */
input:required {
    border-color: red;
}

/* Valid/Invalid inputs */
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

### Structural Pseudo-classes:
```css
/* First child */
li:first-child {
    font-weight: bold;
}

/* Last child */
li:last-child {
    margin-bottom: 0;
}

/* Nth child */
tr:nth-child(even) {
    background-color: #f2f2f2;
}

tr:nth-child(odd) {
    background-color: #fff;
}

/* Nth of type */
p:nth-of-type(3) {
    color: red;
}

/* First of type */
img:first-of-type {
    margin-top: 0;
}
```

### Content Pseudo-classes:
```css
/* Empty elements */
div:empty {
    display: none;
}

/* Elements containing specific content */
p:contains("important") {
    font-weight: bold;
}

/* Not selector */
:not(.excluded) {
    display: block;
}
```

## 6. Descendant Selectors

### Basic Descendant Selectors:
```css
/* All paragraphs inside articles */
article p {
    margin-bottom: 1em;
}

/* Deep nesting */
.container .content .section p {
    color: #333;
}
```

### Child Selectors:
```css
/* Direct children only */
ul > li {
    list-style: none;
}

/* Multiple levels */
nav > ul > li > a {
    text-decoration: none;
}
```

### Adjacent Sibling Selectors:
```css
/* Immediate sibling */
h2 + p {
    font-size: 1.2em;
}

/* General sibling */
h2 ~ p {
    margin-top: 1em;
}
```

## 7. Complex Selector Combinations

### Combining Multiple Types:
```css
/* Element with class and pseudo-class */
button.primary:hover {
    background-color: darkblue;
}

/* Multiple conditions */
input[type="text"]:focus,
input[type="email"]:focus {
    border-color: #007bff;
}

/* Nested elements with states */
.dropdown:hover > .dropdown-menu {
    display: block;
}

/* Complex combinations */
.card .card-header h3:first-child,
.card .card-body p:first-of-type {
    margin-top: 0;
}
```

### Attribute Selectors:
```css
/* Elements with specific attribute */
[disabled] {
    cursor: not-allowed;
}

/* Exact attribute value */
[type="submit"] {
    background-color: green;
}

/* Attribute contains value */
[class*="btn-"] {
    border-radius: 4px;
}

/* Attribute starts with */
[href^="http"] {
    padding-right: 20px;
}

/* Attribute ends with */
[href$=".pdf"] {
    color: red;
}
```

## 8. Best Practices

### Selector Specificity:
```css
/* Good - Low specificity */
.button {
    background: blue;
}

/* Avoid - High specificity */
div#header.active .navigation li.active a {
    color: blue;
}
```

### Naming Conventions:
```css
/* BEM Methodology */
.block {}
.block__element {}
.block--modifier {}

/* Example */
.card {}
.card__title {}
.card__image {}
.card--featured {}
```

### Organization:
```css
/* Group related selectors */
/* Typography */
h1, .h1 { font-size: 2em; }
h2, .h2 { font-size: 1.5em; }

/* Components */
.button { /* ... */ }
.button.primary { /* ... */ }
.button.secondary { /* ... */ }

/* Layout */
.container { /* ... */ }
.grid { /* ... */ }
```

### Performance Considerations:
```css
/* Good - Efficient selectors */
.specific-class {}

/* Avoid - Inefficient selectors */
div > div > div > span {}

/* Good - Specific class */
.navigation-link {}

/* Avoid - Generic element with multiple qualifiers */
nav ul li a {}
```

### Maintainability:
```css
/* Use CSS custom properties */
:root {
    --primary-color: #007bff;
    --spacing-unit: 8px;
}

.element {
    color: var(--primary-color);
    margin: calc(var(--spacing-unit) * 2);
}
```

## 9. Common Examples

### Navigation Menu:
```css
/* Basic navigation */
.nav {
    list-style: none;
    padding: 0;
}

.nav > li {
    display: inline-block;
}

.nav > li > a {
    text-decoration: none;
    padding: 10px 15px;
}

.nav > li > a:hover {
    background-color: #f0f0f0;
}

/* Active state */
.nav > li.active > a {
    font-weight: bold;
}
```

### Form Styles:
```css
/* Form elements */
.form-group {
    margin-bottom: 1rem;
}

.form-control {
    display: block;
    width: 100%;
    padding: 0.375rem 0.75rem;
}

.form-control:focus {
    border-color: #80bdff;
    box-shadow: 0 0 0 0.2rem rgba(0,123,255,.25);
}

/* Invalid state */
.form-control:invalid {
    border-color: #dc3545;
}

/* Required fields */
.form-control:required {
    border-left-width: 3px;
}
```
