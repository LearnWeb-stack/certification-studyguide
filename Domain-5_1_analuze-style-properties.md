# Comprehensive CSS Properties Guide

## 1. Position Property

### Understanding Position Values:

#### Static (Default)
- Elements follow normal document flow
- Top, right, bottom, left properties have no effect
- Most common default behavior

```css
.element {
    position: static;
}
```

#### Relative
- Positions relative to element's normal position
- Creates a positioning context for absolute children
- Maintains space in document flow
- Can be offset using top, right, bottom, left

```css
.element {
    position: relative;
    top: 20px;    /* Moves down 20px from normal position */
    left: 30px;   /* Moves right 30px from normal position */
}
```

#### Absolute
- Removes element from normal document flow
- Positions relative to nearest positioned ancestor
- If no positioned ancestor, positions relative to viewport
- Other elements ignore its space

```css
/* Parent must be positioned for child to position relative to it */
.parent {
    position: relative;
    height: 200px;
}

.child {
    position: absolute;
    top: 50%;          /* 50% from parent's top */
    left: 50%;         /* 50% from parent's left */
    transform: translate(-50%, -50%);  /* Center precisely */
}
```

#### Fixed
- Removes element from normal flow
- Positions relative to viewport
- Stays in place during scrolling
- Common for headers, navigation, modals

```css
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: white;
    z-index: 1000;     /* Controls stacking order */
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
```

#### Sticky
- Hybrid of relative and fixed
- Behaves as relative until scroll threshold
- Then becomes fixed until parent exits viewport
- Useful for section headers, navigation

```css
.section-header {
    position: sticky;
    top: 0;            /* Sticks when reaches top */
    background: white;
    padding: 15px;
    z-index: 100;
}
```

## 2. Float Property

### Understanding Float:
- Removes element from normal flow
- Pushes element to left or right
- Other elements wrap around it
- Parent may need clearfix

#### Basic Float Usage
```css
/* Float elements */
.image {
    float: left;
    margin: 0 20px 20px 0;  /* Space around floated element */
}

/* Clear floated elements */
.clear {
    clear: both;  /* Prevents wrapping around floats */
}

/* Clearfix for parent */
.parent::after {
    content: "";
    display: table;
    clear: both;
}
```

#### Common Float Problems and Solutions:
```css
/* Parent collapse prevention */
.container {
    overflow: hidden;  /* Method 1 */
}

.container::after {    /* Method 2 - Clearfix */
    content: "";
    display: table;
    clear: both;
}

/* Equal height columns */
.column {
    float: left;
    width: 33.33%;
    padding-bottom: 9999px;
    margin-bottom: -9999px;
}
```

## 3. Width and Height Properties

### Understanding Dimensions:

#### Width Types
```css
.element {
    /* Fixed width */
    width: 300px;      /* Exact pixel width */
    
    /* Percentage width */
    width: 50%;        /* 50% of parent's width */
    
    /* Viewport width */
    width: 100vw;      /* 100% of viewport width */
    
    /* Auto width */
    width: auto;       /* Default - fits content */
    
    /* Max/Min constraints */
    max-width: 1200px; /* Maximum allowed width */
    min-width: 320px;  /* Minimum allowed width */
}
```

#### Height Types
```css
.element {
    /* Fixed height */
    height: 200px;     /* Exact pixel height */
    
    /* Percentage height */
    height: 100%;      /* Requires parent height */
    
    /* Viewport height */
    height: 100vh;     /* 100% of viewport height */
    
    /* Auto height */
    height: auto;      /* Fits content height */
    
    /* Max/Min constraints */
    max-height: 800px; /* Maximum allowed height */
    min-height: 200px; /* Minimum allowed height */
}
```

## 4. Overflow Property

### Understanding Overflow:
- Controls how content behaves when it exceeds container
- Affects both x and y axes
- Can be controlled separately per axis

#### Overflow Values
```css
.container {
    /* Hidden overflow */
    overflow: hidden;  /* Clips excess content */
    
    /* Scroll overflow */
    overflow: scroll;  /* Always shows scrollbars */
    
    /* Auto overflow */
    overflow: auto;    /* Scrollbars when needed */
    
    /* Visible overflow */
    overflow: visible; /* Content shows outside container */
    
    /* Axis-specific overflow */
    overflow-x: hidden;
    overflow-y: auto;
}
```

#### Common Use Cases:
```css
/* Text truncation */
.truncate {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

/* Scrollable container */
.scroll-box {
    height: 300px;
    overflow-y: auto;
    padding: 20px;
    border: 1px solid #ddd;
}
```

## 5. Display Property

### Understanding Display Types:

#### Block
- Takes full width available
- Creates line break before and after
- Can have width and height

```css
.block {
    display: block;
    width: 80%;
    margin: 20px auto;
}
```

#### Inline
- Takes only needed width
- No line breaks
- Cannot have width/height
- Respects left & right margins/padding, not top & bottom

```css
.inline {
    display: inline;
    margin: 0 10px;  /* Only left/right margin works */
}
```

#### Inline-Block
- Inline flow but can have block properties
- Can have width/height
- No line break
- Respects all margins/padding

```css
.inline-block {
    display: inline-block;
    width: 200px;
    height: 100px;
    margin: 10px;
    vertical-align: top;
}
```

#### Flex
- Creates flexible box model
- Controls child alignment and order
- One-dimensional layout

```css
.flex-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}
```

#### Grid
- Creates grid-based layout
- Two-dimensional layout
- Controls rows and columns

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    padding: 20px;
}
```

## 6. Box Model

### Understanding Box Model Components:

#### Content Box
- Actual content area
- Affected by width/height

```css
.content-box {
    width: 300px;     /* Content width */
    height: 200px;    /* Content height */
    box-sizing: content-box;  /* Default */
}
```

#### Padding Box
- Space between content and border
- Increases element size
- Can be transparent or colored

```css
.padding-box {
    padding: 20px;              /* All sides */
    padding: 20px 30px;         /* Vertical | Horizontal */
    padding: 10px 20px 15px;    /* Top | Horizontal | Bottom */
    padding: 10px 20px 15px 25px; /* Top | Right | Bottom | Left */
}
```

#### Border Box
- Line around padding box
- Can have style, width, color
- Adds to element size

```css
.border-box {
    border: 1px solid black;   /* Width | Style | Color */
    border-radius: 4px;        /* Rounded corners */
    box-sizing: border-box;    /* Width/height includes padding/border */
}
```

#### Margin Box
- Space outside border
- Creates gaps between elements
- Can be negative

```css
.margin-box {
    margin: 20px;              /* All sides */
    margin: auto;              /* Center horizontally */
    margin: 20px auto;         /* Vertical | Horizontal center */
}
```

## 7. Alignment

### Understanding Alignment Methods:

#### Text Alignment
```css
.text {
    text-align: left;      /* Left align text */
    text-align: center;    /* Center align text */
    text-align: right;     /* Right align text */
    text-align: justify;   /* Justify text */
}
```

#### Flex Alignment
```css
.flex-container {
    display: flex;
    
    /* Main axis alignment */
    justify-content: flex-start;    /* Start of main axis */
    justify-content: center;        /* Center of main axis */
    justify-content: flex-end;      /* End of main axis */
    justify-content: space-between; /* Space between items */
    
    /* Cross axis alignment */
    align-items: stretch;     /* Default - stretch to fill */
    align-items: center;      /* Center on cross axis */
    align-items: flex-start;  /* Start of cross axis */
    align-items: flex-end;    /* End of cross axis */
}
```

#### Grid Alignment
```css
.grid-container {
    display: grid;
    
    /* Align grid items */
    justify-items: center;     /* Center horizontally */
    align-items: center;       /* Center vertically */
    
    /* Align entire grid */
    justify-content: center;   /* Center grid horizontally */
    align-content: center;     /* Center grid vertically */
    
    /* Shorthand */
    place-items: center;       /* Center both axes */
}
```

## 8. Common Layout Techniques

### Centering Techniques:

#### Horizontal Centering
```css
/* Block elements */
.center-block {
    width: 80%;
    margin: 0 auto;
}

/* Inline/Inline-block elements */
.center-inline {
    text-align: center;
}

/* Flex centering */
.center-flex {
    display: flex;
    justify-content: center;
}
```

#### Vertical Centering
```css
/* Using position */
.center-position {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}

/* Using flex */
.center-flex {
    display: flex;
    align-items: center;
    min-height: 100vh;
}

/* Using grid */
.center-grid {
    display: grid;
    place-items: center;
    min-height: 100vh;
}
```

### Responsive Layouts:
```css
/* Responsive container */
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Responsive grid */
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

/* Responsive flex */
.flex {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.flex-item {
    flex: 1 1 300px;  /* Grow | Shrink | Basis */
}
```

### Best Practices:

1. Box Sizing:
```css
/* Apply border-box to all elements */
* {
    box-sizing: border-box;
}
```

2. Responsive Images:
```css
img {
    max-width: 100%;
    height: auto;
}
```

3. Mobile-First Media Queries:
```css
/* Base styles for mobile */
.element {
    width: 100%;
}

/* Tablet styles */
@media (min-width: 768px) {
    .element {
        width: 50%;
    }
}

/* Desktop styles */
@media (min-width: 1024px) {
    .element {
        width: 33.33%;
    }
}
```
