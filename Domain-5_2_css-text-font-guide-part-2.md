# CSS Text and Font Properties Guide

## 1. Font-Family Property

### Syntax and Values:
```css
.element {
    /* Single font */
    font-family: Arial;
    
    /* Font stack */
    font-family: Arial, Helvetica, sans-serif;
    
    /* Generic family */
    font-family: sans-serif;
    font-family: serif;
    font-family: monospace;
    font-family: cursive;
    font-family: fantasy;
    font-family: system-ui;
}
```

### Best Practices:
```css
/* Web-safe font stack */
body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 
                 Roboto, Oxygen, Ubuntu, Cantarell, 
                 'Open Sans', 'Helvetica Neue', sans-serif;
}

/* With custom web fonts */
@font-face {
    font-family: 'CustomFont';
    src: url('custom-font.woff2') format('woff2'),
         url('custom-font.woff') format('woff');
}

.custom-text {
    font-family: 'CustomFont', Arial, sans-serif;
}
```

## 2. Color Property

### Available Values:
```css
.element {
    /* Named colors */
    color: red;
    color: blue;
    color: transparent;
    
    /* Hex values */
    color: #ff0000;
    color: #f00;  /* Shorthand */
    
    /* RGB values */
    color: rgb(255, 0, 0);
    color: rgba(255, 0, 0, 0.5);  /* With opacity */
    
    /* HSL values */
    color: hsl(0, 100%, 50%);
    color: hsla(0, 100%, 50%, 0.5);  /* With opacity */
    
    /* Current color */
    color: currentColor;
    
    /* Inherit from parent */
    color: inherit;
}
```

### Color Variables:
```css
:root {
    --primary-color: #007bff;
    --text-color: #333;
    --light-text: #666;
}

.element {
    color: var(--primary-color);
}
```

## 3. Font-Style Property

### Available Values:
```css
.element {
    /* Normal */
    font-style: normal;
    
    /* Italic */
    font-style: italic;
    
    /* Oblique */
    font-style: oblique;
    
    /* Oblique with angle */
    font-style: oblique 14deg;
}
```

## 4. Font-Size Property

### Available Values:
```css
.element {
    /* Absolute sizes */
    font-size: 16px;
    font-size: 1em;
    font-size: 1rem;
    font-size: 12pt;
    
    /* Relative sizes */
    font-size: larger;
    font-size: smaller;
    font-size: 150%;
    
    /* Viewport units */
    font-size: 5vw;
    
    /* Keywords */
    font-size: xx-small;
    font-size: x-small;
    font-size: small;
    font-size: medium;
    font-size: large;
    font-size: x-large;
    font-size: xx-large;
}
```

### Responsive Font Sizes:
```css
/* Fluid Typography */
html {
    font-size: 16px;
}

@media screen and (min-width: 320px) {
    html {
        font-size: calc(16px + 6 * ((100vw - 320px) / 680));
    }
}

@media screen and (min-width: 1000px) {
    html {
        font-size: 22px;
    }
}
```

## 5. Font-Weight Property

### Available Values:
```css
.element {
    /* Numeric values */
    font-weight: 100;  /* Thin */
    font-weight: 200;  /* Extra Light */
    font-weight: 300;  /* Light */
    font-weight: 400;  /* Normal */
    font-weight: 500;  /* Medium */
    font-weight: 600;  /* Semi Bold */
    font-weight: 700;  /* Bold */
    font-weight: 800;  /* Extra Bold */
    font-weight: 900;  /* Black */
    
    /* Keywords */
    font-weight: normal;
    font-weight: bold;
    font-weight: lighter;
    font-weight: bolder;
}
```

## 6. Font-Variant Property

### Available Values:
```css
.element {
    /* Basic variants */
    font-variant: normal;
    font-variant: small-caps;
    
    /* Multiple features */
    font-variant: small-caps slashed-zero;
    
    /* Numeric variants */
    font-variant-numeric: ordinal;
    font-variant-numeric: slashed-zero;
    font-variant-numeric: lining-nums;
    font-variant-numeric: oldstyle-nums;
    
    /* Ligatures */
    font-variant-ligatures: common-ligatures;
    font-variant-ligatures: no-common-ligatures;
    font-variant-ligatures: discretionary-ligatures;
}
```

## 7. Link Colors

### Link States:
```css
/* Basic link colors */
a {
    color: #007bff;  /* Unvisited */
}

a:visited {
    color: #6610f2;  /* Visited */
}

a:hover {
    color: #0056b3;  /* Mouse over */
}

a:active {
    color: #003980;  /* Clicking */
}

/* Modern link styling */
.modern-link {
    color: currentColor;
    text-decoration: none;
    border-bottom: 1px solid currentColor;
    transition: border-color 0.3s ease;
}

.modern-link:hover {
    border-color: transparent;
}
```

## 8. Text Formatting

### Text-Transform:
```css
.element {
    text-transform: none;
    text-transform: capitalize;
    text-transform: uppercase;
    text-transform: lowercase;
}
```

### White-Space:
```css
.element {
    white-space: normal;
    white-space: nowrap;
    white-space: pre;
    white-space: pre-wrap;
    white-space: pre-line;
}
```

## 9. Text Alignment

### Available Values:
```css
.element {
    /* Basic alignment */
    text-align: left;
    text-align: right;
    text-align: center;
    text-align: justify;
    
    /* Advanced alignment */
    text-align-last: auto;
    text-align-last: left;
    text-align-last: right;
    text-align-last: center;
    text-align-last: justify;
}
```

## 10. Text Decoration

### Available Properties:
```css
.element {
    /* Single property */
    text-decoration: underline;
    
    /* Multiple values */
    text-decoration: underline dotted red;
    
    /* Individual properties */
    text-decoration-line: underline;
    text-decoration-style: dotted;
    text-decoration-color: red;
    text-decoration-thickness: 2px;
    
    /* Multiple lines */
    text-decoration-line: underline overline;
}
```

## 11. Text Indentation

### Available Values:
```css
.element {
    /* Length values */
    text-indent: 50px;
    text-indent: 2em;
    
    /* Percentage */
    text-indent: 10%;
    
    /* Negative values */
    text-indent: -100px;
    
    /* Hanging indentation */
    text-indent: -2em;
    padding-left: 2em;
}
```

## 12. Line-Height

### Available Values:
```css
.element {
    /* Unitless (recommended) */
    line-height: 1.5;
    
    /* Length */
    line-height: 20px;
    line-height: 2em;
    
    /* Percentage */
    line-height: 150%;
    
    /* Keywords */
    line-height: normal;
}
```

## 13. Word-Wrap and Overflow

### Word-Wrap:
```css
.element {
    /* Basic word wrap */
    word-wrap: normal;
    word-wrap: break-word;
    
    /* Overflow wrap (modern) */
    overflow-wrap: normal;
    overflow-wrap: break-word;
    overflow-wrap: anywhere;
    
    /* Word break */
    word-break: normal;
    word-break: break-all;
    word-break: keep-all;
}
```

## 14. Letter-Spacing

### Available Values:
```css
.element {
    /* Normal */
    letter-spacing: normal;
    
    /* Length values */
    letter-spacing: 2px;
    letter-spacing: 0.2em;
    letter-spacing: -1px;
}
```

## Practical Examples:

### 1. Typography System:
```css
:root {
    /* Font sizes */
    --font-size-xs: 0.75rem;
    --font-size-sm: 0.875rem;
    --font-size-md: 1rem;
    --font-size-lg: 1.125rem;
    --font-size-xl: 1.25rem;
    
    /* Line heights */
    --line-height-tight: 1.25;
    --line-height-normal: 1.5;
    --line-height-relaxed: 1.75;
    
    /* Letter spacing */
    --letter-spacing-tight: -0.025em;
    --letter-spacing-normal: 0;
    --letter-spacing-wide: 0.025em;
}

/* Headings */
h1 {
    font-size: var(--font-size-xl);
    line-height: var(--line-height-tight);
    letter-spacing: var(--letter-spacing-tight);
    font-weight: 700;
}

/* Body text */
p {
    font-size: var(--font-size-md);
    line-height: var(--line-height-normal);
    letter-spacing: var(--letter-spacing-normal);
}
```

### 2. Article Typography:
```css
.article {
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 1.125rem;
    line-height: 1.7;
    color: #2d3748;
}

.article h2 {
    font-family: -apple-system, BlinkMacSystemFont, sans-serif;
    font-size: 1.75rem;
    font-weight: 600;
    margin-top: 2em;
    letter-spacing: -0.025em;
}

.article p {
    margin-bottom: 1.5em;
    text-align: justify;
    text-indent: 1em;
}

.article blockquote {
    font-style: italic;
    border-left: 3px solid #cbd5e0;
    padding-left: 1em;
    margin-left: 0;
}
```

### 3. Link Styling:
```css
.custom-link {
    color: #2b6cb0;
    text-decoration: none;
    border-bottom: 1px solid transparent;
    transition: all 0.2s ease;
}

.custom-link:hover {
    color: #2c5282;
    border-bottom-color: currentColor;
}

.custom-link:active {
    color: #2a4365;
}
```

### 4. Responsive Text:
```css
/* Fluid typography */
.fluid-text {
    font-size: clamp(1rem, 0.5rem + 2vw, 2rem);
    line-height: clamp(1.5, 1.2 + 1vw, 2);
    letter-spacing: clamp(0.02em, 0.01em + 0.05vw, 0.05em);
}
```

### 5. Truncation:
```css
.truncate {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    max-width: 100%;
}

.line-clamp {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
```

