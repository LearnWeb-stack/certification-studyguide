# CSS Border and Background Properties Guide

## 1. Border Properties

### border-color
Defines the color of element borders. Can be set for individual sides or all at once.

#### Property Values:
```css
.element {
    /* Single color for all sides */
    border-color: red;
    
    /* Individual sides (top, right, bottom, left) */
    border-color: red blue green yellow;
    
    /* Color formats */
    border-color: #ff0000;            /* Hex */
    border-color: rgb(255, 0, 0);     /* RGB */
    border-color: hsl(0, 100%, 50%);  /* HSL */
    
    /* Transparency */
    border-color: transparent;        /* Fully transparent */
    border-color: rgba(255,0,0,0.5); /* Semi-transparent */
    
    /* Current color */
    border-color: currentColor;       /* Inherits text color */
}

/* Individual side colors */
.element {
    border-top-color: red;
    border-right-color: blue;
    border-bottom-color: green;
    border-left-color: yellow;
}
```

#### Use Cases:
```css
/* Highlight active element */
.button {
    border-color: #ccc;
}
.button:hover {
    border-color: #333;
}

/* Color-coded status */
.status-success {
    border-color: #28a745;
}
.status-error {
    border-color: #dc3545;
}

/* Gradient border using border-image */
.gradient-border {
    border-color: transparent;
    border-image: linear-gradient(45deg, red, blue) 1;
}
```

### border-style
Controls the line style of borders. Different styles serve different visual purposes.

#### Property Values and Their Uses:
```css
.element {
    /* Basic styles */
    border-style: solid;    /* Most common - solid line */
    border-style: dashed;   /* Series of rectangular dashes */
    border-style: dotted;   /* Series of round dots */
    border-style: double;   /* Two parallel solid lines */
    
    /* Decorative styles */
    border-style: groove;   /* 3D grooved effect - appears carved in */
    border-style: ridge;    /* 3D ridged effect - appears raised */
    border-style: inset;    /* 3D inset effect - appears pressed in */
    border-style: outset;   /* 3D outset effect - appears raised */
    
    /* Special values */
    border-style: none;     /* No border displayed */
    border-style: hidden;   /* Similar to none, but wins in border conflicts */
    
    /* Mixed styles */
    border-style: solid dashed dotted double;  /* top right bottom left */
}

/* Individual side styles */
.element {
    border-top-style: solid;
    border-right-style: dashed;
    border-bottom-style: dotted;
    border-left-style: double;
}
```

#### Practical Examples:
```css
/* Button styles */
.button {
    /* Basic button */
    border-style: solid;
}

/* Focus indication */
.input:focus {
    border-style: double;  /* Double border for emphasis */
}

/* Decorative panel */
.panel {
    border-style: ridge;  /* 3D raised effect */
}

/* Mixed styles for emphasis */
.highlight-box {
    border-style: solid dashed;  /* Solid top/bottom, dashed sides */
}
```

### border-width
Defines thickness of borders. Can use different units and values for different sides.

#### Property Values:
```css
.element {
    /* Predefined values */
    border-width: thin;     /* Usually 1px */
    border-width: medium;   /* Usually 3px */
    border-width: thick;    /* Usually 5px */
    
    /* Length units */
    border-width: 1px;      /* Pixels */
    border-width: 0.1em;    /* Relative to font-size */
    border-width: 0.1rem;   /* Relative to root font-size */
    
    /* Multiple values */
    border-width: 1px 2px;             /* vertical horizontal */
    border-width: 1px 2px 3px;         /* top horizontal bottom */
    border-width: 1px 2px 3px 4px;     /* top right bottom left */
}

/* Individual side widths */
.element {
    border-top-width: 1px;
    border-right-width: 2px;
    border-bottom-width: 3px;
    border-left-width: 4px;
}
```

## 2. Background Properties

### background-color
Sets the background color of an element.

#### Property Values:
```css
.element {
    /* Named colors */
    background-color: red;
    background-color: transparent;
    
    /* Hex values */
    background-color: #ff0000;
    background-color: #f00;  /* Shorthand */
    
    /* RGB/RGBA values */
    background-color: rgb(255, 0, 0);
    background-color: rgba(255, 0, 0, 0.5);  /* With opacity */
    
    /* HSL/HSLA values */
    background-color: hsl(0, 100%, 50%);
    background-color: hsla(0, 100%, 50%, 0.5);  /* With opacity */
}
```

### background-image
Sets one or more background images.

#### Property Values and Use Cases:
```css
.element {
    /* Single image */
    background-image: url('image.jpg');
    
    /* Multiple images */
    background-image: url('overlay.png'), url('background.jpg');
    
    /* Gradients */
    background-image: linear-gradient(to right, red, blue);
    background-image: radial-gradient(circle, red, blue);
    background-image: conic-gradient(from 45deg, red, blue);
    
    /* Complex gradients */
    background-image: linear-gradient(
        45deg,
        rgba(255,0,0,0.5),
        rgba(0,0,255,0.5)
    );
}
```

### background-position
Controls the starting position of background images.

#### Property Values:
```css
.element {
    /* Keywords */
    background-position: top;
    background-position: right;
    background-position: bottom;
    background-position: left;
    background-position: center;
    
    /* Combined keywords */
    background-position: top right;
    background-position: bottom left;
    
    /* Percentages */
    background-position: 50% 50%;  /* Center */
    background-position: 0% 0%;    /* Top left */
    background-position: 100% 100%; /* Bottom right */
    
    /* Length units */
    background-position: 20px 30px;
    background-position: 1em 2em;
    
    /* Multiple backgrounds */
    background-position: right 10px top 20px, center;
}
```

### background-size
Controls how background images are sized.

#### Property Values:
```css
.element {
    /* Keywords */
    background-size: auto;      /* Original size */
    background-size: cover;     /* Covers entire container */
    background-size: contain;   /* Fits inside container */
    
    /* Length values */
    background-size: 300px 200px;
    background-size: 50% 50%;
    
    /* Mixed values */
    background-size: auto 75%;
    
    /* Multiple backgrounds */
    background-size: cover, contain;
}
```

### background-repeat
Controls how background images repeat.

#### Property Values:
```css
.element {
    /* Basic values */
    background-repeat: repeat;      /* Default - repeats both directions */
    background-repeat: no-repeat;   /* No repetition */
    background-repeat: repeat-x;    /* Repeats horizontally */
    background-repeat: repeat-y;    /* Repeats vertically */
    
    /* Space-saving values */
    background-repeat: space;      /* Images evenly spaced */
    background-repeat: round;      /* Images adjusted to fit */
    
    /* Two-value syntax */
    background-repeat: repeat space;  /* horizontal vertical */
}
```

### background-attachment
Determines if background scrolls with content.

#### Property Values:
```css
.element {
    background-attachment: scroll;  /* Scrolls with content */
    background-attachment: fixed;   /* Fixed to viewport */
    background-attachment: local;   /* Scrolls with element's contents */
}
```

### Shorthand background Property
Combines all background properties in one declaration.

```css
.element {
    /* Order: color image position/size repeat attachment */
    background: #ff0000 url('image.jpg') center/cover no-repeat fixed;
    
    /* Multiple backgrounds */
    background: 
        url('overlay.png') center/contain no-repeat,
        url('background.jpg') center/cover no-repeat;
}
```

## 3. Practical Examples

### Card with Border and Background:
```css
.card {
    /* Border properties */
    border-width: 1px;
    border-style: solid;
    border-color: #ddd;
    
    /* Background properties */
    background-color: white;
    background-image: linear-gradient(to bottom, #f8f9fa, white);
    background-repeat: no-repeat;
    
    /* Shorthand */
    border: 1px solid #ddd;
    background: linear-gradient(to bottom, #f8f9fa, white) no-repeat;
}
```

### Hero Section:
```css
.hero {
    /* Background image with overlay */
    background: 
        linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
        url('hero.jpg') center/cover no-repeat fixed;
    
    /* Border bottom for separation */
    border-bottom: 3px solid #007bff;
}
```

### Interactive Button:
```css
.button {
    /* Default state */
    border: 2px solid #007bff;
    background-color: transparent;
    transition: all 0.3s ease;
    
    /* Hover state */
    &:hover {
        border-color: #0056b3;
        background-color: #007bff;
        color: white;
    }
    
    /* Active state */
    &:active {
        border-color: #004085;
        background-color: #0056b3;
    }
}
```
