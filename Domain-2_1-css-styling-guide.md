# CSS Styling Methods and Precedence Guide

## 1. CSS Implementation Methods

### A. Inline Styles

#### Syntax:
```html
<element style="property: value;">
```

#### Examples:
```html
<!-- Basic inline style -->
<div style="color: blue; font-size: 16px;">
    Blue text content
</div>

<!-- Multiple properties -->
<p style="
    color: #333;
    font-size: 18px;
    margin: 20px;
    padding: 10px;
    border: 1px solid #ddd;
    background-color: #f9f9f9;
">
    Styled paragraph
</p>

<!-- Complex inline styles -->
<div style="
    background: linear-gradient(to right, #ff0000, #00ff00);
    transform: rotate(45deg);
    box-shadow: 2px 2px 5px rgba(0,0,0,0.3);
">
    Complex styled element
</div>
```

#### When to Use:
1. Quick prototyping
2. Email templates
3. Single-use styles
4. Dynamic styling with JavaScript
5. Override specific instances

#### Pros:
- Highest specificity
- Immediate effect
- Good for email templates
- Useful for dynamic styles

#### Cons:
- Poor maintainability
- Code repetition
- No reusability
- Mixing content and presentation

### B. Internal (Embedded) Style Sheets

#### Syntax:
```html
<head>
    <style type="text/css">
        selector {
            property: value;
        }
    </style>
</head>
```

#### Examples:
```html
<head>
    <style>
        /* Basic styles */
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
        }

        /* Class styles */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* ID styles */
        #header {
            background-color: #333;
            color: white;
            padding: 1rem;
        }

        /* Nested styles */
        .article {
            margin-bottom: 20px;
        }
        .article h2 {
            color: #333;
            margin-bottom: 10px;
        }
        .article p {
            color: #666;
        }

        /* Media queries */
        @media (max-width: 768px) {
            .container {
                padding: 0 10px;
            }
        }
    </style>
</head>
```

#### When to Use:
1. Single-page websites
2. Quick prototypes
3. Page-specific styles
4. Small projects
5. Testing and debugging

#### Pros:
- No external files needed
- Faster loading for small sites
- Page-specific styles
- Easy to maintain for small projects
- Good for prototypes

#### Cons:
- Increases HTML file size
- No caching benefits
- Code duplication across pages
- Mixing structure and presentation
- Harder to maintain in large projects

### C. External Style Sheets

#### Syntax:
```html
<!-- In HTML file -->
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

```css
/* In styles.css */
selector {
    property: value;
}
```

#### Examples:

1. Basic External CSS (styles.css):
```css
/* Reset defaults */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Base styles */
body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Layout */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
}

/* Components */
.button {
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border-radius: 4px;
    text-decoration: none;
}

/* Utilities */
.mt-20 {
    margin-top: 20px;
}

/* Media queries */
@media (max-width: 768px) {
    .container {
        padding: 0 10px;
    }
}
```

2. Multiple CSS Files:
```html
<head>
    <!-- Reset CSS -->
    <link rel="stylesheet" href="reset.css">
    
    <!-- Main styles -->
    <link rel="stylesheet" href="main.css">
    
    <!-- Component styles -->
    <link rel="stylesheet" href="components.css">
    
    <!-- Page-specific styles -->
    <link rel="stylesheet" href="home.css">
    
    <!-- Media queries -->
    <link rel="stylesheet" href="responsive.css">
</head>
```

#### When to Use:
1. Large projects
2. Multiple pages
3. Team development
4. Maintainable codebase
5. Production environments

#### Pros:
- Better organization
- Code reusability
- Browser caching
- Easier maintenance
- Separation of concerns

#### Cons:
- Additional HTTP requests
- Setup required
- Potential for conflicting styles
- File management needed

## 2. CSS Precedence (Cascade)

### Priority Order (Highest to Lowest):

1. Important Declarations:
```css
/* Highest priority */
.element {
    color: red !important;
}
```

2. Inline Styles:
```html
<div style="color: blue;">
```

3. IDs:
```css
#unique-element {
    color: green;
}
```

4. Classes, Attributes, and Pseudo-classes:
```css
.my-class {
    color: yellow;
}
[type="text"] {
    color: orange;
}
:hover {
    color: purple;
}
```

5. Elements and Pseudo-elements:
```css
p {
    color: brown;
}
::before {
    content: "→";
}
```

6. Universal Selector:
```css
* {
    color: black;
}
```

### Specificity Examples:

```css
/* Specificity: 1-0-0 */
#header {
    color: black;
}

/* Specificity: 0-1-0 */
.header {
    color: blue;
}

/* Specificity: 0-2-0 */
.header.active {
    color: red;
}

/* Specificity: 0-1-1 */
.header h1 {
    color: green;
}

/* Specificity: 0-0-2 */
div p {
    color: yellow;
}
```

## 3. Browser Default Styles

### Common Browser Defaults:

```css
/* Reset default margins and padding */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Reset headings */
h1, h2, h3, h4, h5, h6 {
    font-size: 1em;
    font-weight: normal;
}

/* Reset lists */
ul, ol {
    list-style: none;
}

/* Reset links */
a {
    text-decoration: none;
    color: inherit;
}

/* Reset form elements */
button,
input,
select,
textarea {
    font-family: inherit;
    font-size: 100%;
    margin: 0;
}
```

### Modern CSS Reset Example:
```css
/* Modern CSS Reset */

/* Use a more intuitive box-sizing model */
*,
*::before,
*::after {
    box-sizing: border-box;
}

/* Remove default margin */
body,
h1,
h2,
h3,
h4,
p,
figure,
blockquote,
dl,
dd {
    margin: 0;
}

/* Set core root defaults */
html:focus-within {
    scroll-behavior: smooth;
}

/* Set core body defaults */
body {
    min-height: 100vh;
    text-rendering: optimizeSpeed;
    line-height: 1.5;
}

/* Make images easier to work with */
img,
picture {
    max-width: 100%;
    display: block;
}

/* Inherit fonts for inputs and buttons */
input,
button,
textarea,
select {
    font: inherit;
}

/* Remove animations for people who've turned them off */
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
}
```

## 4. Best Practices

1. Organization:
```css
/* Group related styles */
/* Layout */
.container {...}
.grid {...}
.flex {...}

/* Components */
.button {...}
.card {...}
.modal {...}

/* Utilities */
.mt-20 {...}
.text-center {...}
.hidden {...}
```

2. Naming Conventions:
```css
/* BEM methodology */
.block {}
.block__element {}
.block--modifier {}

/* Example */
.card {}
.card__title {}
.card__image {}
.card--featured {}
```

3. Media Queries:
```css
/* Mobile-first approach */
.element {
    /* Base styles */
}

@media (min-width: 768px) {
    .element {
        /* Tablet styles */
    }
}

@media (min-width: 1024px) {
    .element {
        /* Desktop styles */
    }
}
```

4. Performance:
```css
/* Use efficient selectors */
.specific-class {} /* Good */
div > div > span {} /* Avoid */

/* Avoid universal selectors */
* {} /* Use sparingly */

/* Minimize specificity conflicts */
.button {} /* Good */
#header .nav .button {} /* Avoid */
```

5. Maintainability:
```css
/* Use CSS variables */
:root {
    --primary-color: #007bff;
    --spacing-unit: 8px;
}

.element {
    color: var(--primary-color);
    margin: calc(var(--spacing-unit) * 2);
}
```

