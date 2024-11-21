# CSS Units, Responsive Design, and Grid Systems Guide

## 1. Units of Measurement

### Absolute Units
Fixed measurements that remain constant regardless of screen size or parent element.

#### Pixels (px):
```css
/* Direct pixel values */
.element {
    width: 200px;          /* Exact width */
    height: 100px;         /* Exact height */
    padding: 20px;         /* Fixed padding */
    font-size: 16px;       /* Fixed font size */
}

/* Use Cases:
   - Border widths
   - Fixed-size elements
   - When exact precision is needed
*/
```

#### Other Absolute Units:
```css
.element {
    /* Points (1pt = 1/72 inch) */
    font-size: 12pt;   /* Common in print stylesheets */
    
    /* Inches */
    margin: 1in;       /* Physical inch measurement */
    
    /* Centimeters */
    padding: 2cm;      /* Physical centimeter measurement */
    
    /* Millimeters */
    border-width: 3mm; /* Physical millimeter measurement */
}
```

### Relative Units
Scale based on other factors like parent element size or viewport dimensions.

#### Em (em):
Relative to parent element's font size.
```css
/* Parent element */
.parent {
    font-size: 16px;
}

/* Child elements */
.child {
    /* If parent is 16px: */
    font-size: 1.5em;     /* 24px (16px × 1.5) */
    margin: 1em;          /* 24px (based on element's font size) */
    padding: 0.5em;       /* 12px (based on element's font size) */
}

/* Compounding example */
.nested {
    font-size: 1.5em;     /* Each nested level multiplies */
}
```

#### Root Em (rem):
Relative to root element's font size (usually html element).
```css
/* Root element */
html {
    font-size: 16px;      /* Base size for rem calculations */
}

/* Any element */
.element {
    /* All calculations based on root 16px */
    font-size: 1.5rem;    /* 24px */
    margin: 1rem;         /* 16px */
    padding: 0.5rem;      /* 8px */
}

/* Responsive font sizing */
html {
    font-size: 16px;
}

@media (max-width: 768px) {
    html {
        font-size: 14px; /* All rem values scale down */
    }
}
```

#### Viewport Units:
Scale based on viewport dimensions.

```css
.element {
    /* Viewport Width (vw) */
    width: 50vw;          /* 50% of viewport width */
    font-size: 5vw;       /* 5% of viewport width */
    
    /* Viewport Height (vh) */
    height: 100vh;        /* Full viewport height */
    margin-top: 10vh;     /* 10% of viewport height */
    
    /* Viewport Min (vmin) */
    width: 50vmin;        /* 50% of smaller viewport dimension */
    
    /* Viewport Max (vmax) */
    height: 50vmax;       /* 50% of larger viewport dimension */
    
    /* Dynamic combination */
    font-size: calc(16px + 1vw);  /* Fluid typography */
}
```

#### Percentages (%):
Relative to parent element's dimensions.
```css
.parent {
    width: 800px;
    height: 600px;
}

.child {
    width: 50%;           /* 400px (50% of parent width) */
    height: 75%;          /* 450px (75% of parent height) */
    margin: 10%;          /* 80px (10% of parent width) */
    padding: 5%;          /* 40px (5% of parent width) */
}
```

## 2. Viewport and Media Queries

### Viewport Meta Tag:
```html
<!-- Responsive viewport meta tag -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Media Query Syntax:
```css
/* Basic media query structure */
@media [type] ([feature]) {
    /* CSS rules */
}

/* Media Types */
@media screen { /* For screens */ }
@media print { /* For printing */ }
@media speech { /* For screen readers */ }
@media all { /* Default - all media types */ }

/* Media Features */
@media (min-width: 768px) { /* Width-based */ }
@media (orientation: landscape) { /* Orientation-based */ }
@media (prefers-color-scheme: dark) { /* User preference */ }
```

### Common Breakpoints:
```css
/* Mobile First Approach */

/* Base styles (mobile) */
.element {
    width: 100%;
    padding: 1rem;
}

/* Tablet (768px and up) */
@media (min-width: 768px) {
    .element {
        width: 50%;
        padding: 2rem;
    }
}

/* Desktop (1024px and up) */
@media (min-width: 1024px) {
    .element {
        width: 33.333%;
        padding: 3rem;
    }
}

/* Large Desktop (1440px and up) */
@media (min-width: 1440px) {
    .element {
        max-width: 1200px;
        margin: 0 auto;
    }
}
```

### Complex Media Queries:
```css
/* Combining conditions */
@media (min-width: 768px) and (orientation: landscape) {
    /* Rules for landscape tablets and up */
}

/* Multiple queries */
@media (min-width: 768px), (orientation: landscape) {
    /* Rules for either condition */
}

/* Feature queries */
@supports (display: grid) {
    /* Rules for browsers supporting CSS Grid */
}
```

## 3. Grid Systems

### CSS Grid:
```css
/* Basic Grid Container */
.grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);  /* 12-column grid */
    gap: 20px;                               /* Grid spacing */
}

/* Responsive Grid */
.grid {
    display: grid;
    gap: 20px;
    
    /* Mobile: 1 column */
    grid-template-columns: 1fr;
    
    /* Tablet: 2 columns */
    @media (min-width: 768px) {
        grid-template-columns: repeat(2, 1fr);
    }
    
    /* Desktop: 4 columns */
    @media (min-width: 1024px) {
        grid-template-columns: repeat(4, 1fr);
    }
}

/* Grid Areas */
.layout {
    display: grid;
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
    grid-template-columns: 200px 1fr 1fr;
}

.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.footer { grid-area: footer; }
```

### Flexbox Grid:
```css
/* Flex Container */
.flex-grid {
    display: flex;
    flex-wrap: wrap;
    margin: -10px;  /* Compensate for item margins */
}

/* Flex Items */
.flex-item {
    flex: 0 0 calc(33.333% - 20px);  /* Three columns */
    margin: 10px;
    
    /* Responsive */
    @media (max-width: 768px) {
        flex: 0 0 calc(50% - 20px);  /* Two columns */
    }
    
    @media (max-width: 480px) {
        flex: 0 0 calc(100% - 20px);  /* One column */
    }
}
```

## 4. Framework Examples

### Bootstrap-style Grid:
```css
/* Container */
.container {
    width: 100%;
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
    
    @media (min-width: 576px) { max-width: 540px; }
    @media (min-width: 768px) { max-width: 720px; }
    @media (min-width: 992px) { max-width: 960px; }
    @media (min-width: 1200px) { max-width: 1140px; }
}

/* Row */
.row {
    display: flex;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}

/* Columns */
.col {
    flex: 1 0 0%;
    padding-right: 15px;
    padding-left: 15px;
}

/* Specific columns */
.col-6 { flex: 0 0 50%; }
.col-4 { flex: 0 0 33.333333%; }
.col-3 { flex: 0 0 25%; }
```

### Custom Framework:
```css
/* Modern Custom Grid System */
:root {
    --grid-columns: 12;
    --grid-gap: 20px;
    --container-width: 1200px;
}

.container {
    width: min(var(--container-width), 100% - 2rem);
    margin-inline: auto;
}

.grid {
    display: grid;
    gap: var(--grid-gap);
    grid-template-columns: repeat(
        auto-fit,
        minmax(min(100%, 300px), 1fr)
    );
}

/* Responsive utilities */
.hide-mobile {
    @media (max-width: 768px) {
        display: none;
    }
}

.hide-desktop {
    @media (min-width: 769px) {
        display: none;
    }
}
```

## 5. Best Practices

### Responsive Images:
```css
/* Fluid images */
img {
    max-width: 100%;
    height: auto;
}

/* Art direction */
picture {
    width: 100%;
    
    source {
        width: 100%;
    }
    
    img {
        width: 100%;
        height: auto;
    }
}
```

### Fluid Typography:
```css
/* Modern fluid typography */
:root {
    --fluid-min-width: 320;
    --fluid-max-width: 1200;
    --fluid-min-size: 16;
    --fluid-max-size: 24;
    
    --fluid-size: calc(
        (var(--fluid-min-size) * 1px) +
        (var(--fluid-max-size) - var(--fluid-min-size)) *
        (100vw - (var(--fluid-min-width) * 1px)) /
        (var(--fluid-max-width) - var(--fluid-min-width))
    );
}

body {
    font-size: clamp(
        var(--fluid-min-size) * 1px,
        var(--fluid-size),
        var(--fluid-max-size) * 1px
    );
}
```

### Container Queries:
```css
/* Modern container queries */
.card-container {
    container-type: inline-size;
}

@container (min-width: 400px) {
    .card {
        display: grid;
        grid-template-columns: 200px 1fr;
    }
}
```
