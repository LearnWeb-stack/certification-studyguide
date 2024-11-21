# Detailed CSS Text and Font Properties Guide

## 1. Font-Family
The font-family property defines the typeface that will be used for text. It works as a fallback system, trying each font in order until it finds one available.

### Explanation of Values:
```css
font-family: Arial, Helvetica, sans-serif;
```

- `Arial`: Primary font choice. Browser will try this first
- `Helvetica`: Secondary font, used if Arial isn't available
- `sans-serif`: Generic family, ultimate fallback if no specific fonts are available

### Types of Font Families:
1. Serif Fonts:
   - Have small lines at the ends of characters
   - Example: Times New Roman, Georgia
   - Best for: Traditional, formal content

2. Sans-serif Fonts:
   - Clean, no extra lines
   - Example: Arial, Helvetica
   - Best for: Modern, clean designs

3. Monospace Fonts:
   - Each character takes same width
   - Example: Courier New, Monaco
   - Best for: Code, technical content

4. Cursive Fonts:
   - Mimics handwriting
   - Example: Brush Script, Comic Sans
   - Best for: Informal, creative content

5. Fantasy Fonts:
   - Decorative fonts
   - Example: Impact
   - Best for: Headlines, special effects

```css
/* Example usage with explanation */
.text {
    /* Professional business website */
    font-family: 'Helvetica Neue', Arial, sans-serif;
    /* Explanation:
       1. Tries Helvetica Neue first (common on Mac)
       2. Falls back to Arial (common on Windows)
       3. Uses system sans-serif if others unavailable
    */
}

.code {
    /* Technical documentation */
    font-family: 'Consolas', 'Monaco', monospace;
    /* Explanation:
       1. Consolas (Windows developer font)
       2. Monaco (Mac developer font)
       3. System monospace font as fallback
    */
}
```

## 2. Font-Size
Controls the size of text. Different units can dramatically affect how text scales and responds to different screen sizes.

### Absolute Units:
```css
.text {
    /* Pixels - Fixed size, doesn't scale with user preferences */
    font-size: 16px;  /* Exactly 16 pixels high */
    
    /* Points - Typically for print */
    font-size: 12pt;  /* 1pt = 1/72 inch */
}
```

### Relative Units:
```css
.text {
    /* em - Relative to parent element's font size */
    font-size: 1.2em;  
    /* If parent is 16px, this will be 19.2px (16 × 1.2) */
    
    /* rem - Relative to root element's font size */
    font-size: 1.2rem;
    /* Always relative to html element (usually 16px) */
    
    /* Viewport units */
    font-size: 5vw;  /* 5% of viewport width */
    font-size: 5vh;  /* 5% of viewport height */
}
```

### Keyword Values:
```css
.text {
    font-size: medium;    /* Default size (usually 16px) */
    font-size: small;     /* Smaller than medium */
    font-size: large;     /* Larger than medium */
    font-size: x-large;   /* Even larger */
    font-size: xx-large;  /* Largest */
    font-size: smaller;   /* Smaller than parent */
    font-size: larger;    /* Larger than parent */
}
```

### Responsive Font Sizing:
```css
/* Fluid Typography Example */
.fluid-text {
    /* clamp(minimum, preferred, maximum) */
    font-size: clamp(1rem, 2vw + 1rem, 2rem);
    /* Explanation:
       - Minimum size: 1rem (won't go smaller)
       - Preferred size: 2vw + 1rem (scales with viewport)
       - Maximum size: 2rem (won't go larger)
    */
}
```

## 3. Font-Weight
Controls the thickness of text characters. Can use numeric values (100-900) or keywords.

### Numeric Values Explained:
```css
.text {
    /* Common numeric weights */
    font-weight: 100;  /* Thin - Lightest available */
    font-weight: 300;  /* Light */
    font-weight: 400;  /* Normal/Regular */
    font-weight: 500;  /* Medium */
    font-weight: 700;  /* Bold */
    font-weight: 900;  /* Black - Heaviest available */
}
```

### Keyword Values Explained:
```css
.text {
    /* Normal - Same as 400 */
    font-weight: normal;
    
    /* Bold - Same as 700 */
    font-weight: bold;
    
    /* Relative to parent */
    font-weight: lighter;  /* One weight lighter than parent */
    font-weight: bolder;   /* One weight heavier than parent */
}
```

### Practical Usage:
```css
/* Complete heading system */
h1 {
    font-weight: 700;  /* Bold headings */
}

.subtitle {
    font-weight: 300;  /* Light weight for subtle text */
}

.highlight {
    font-weight: 500;  /* Medium weight for emphasis */
}

/* Variable font weights */
@supports (font-variation-settings: normal) {
    .text {
        font-weight: var(--dynamic-weight, 400);
        /* Supports any value between 100-900 in variable fonts */
    }
}
```

## 4. Color
Defines the color of text. Multiple ways to specify colors, each with specific use cases.

### Color Values Explained:

1. Named Colors:
```css
.text {
    /* Basic named colors */
    color: black;   /* Pure black */
    color: white;   /* Pure white */
    color: red;     /* Pure red */
    
    /* Semantic named colors */
    color: currentColor;  /* Inherits from current element's color */
    color: transparent;   /* Fully transparent */
}
```

2. Hexadecimal (Hex) Colors:
```css
.text {
    /* 6-digit hex */
    color: #FF0000;  /* Red */
    /* Explanation:
       FF = Red (255)
       00 = Green (0)
       00 = Blue (0)
    */
    
    /* 3-digit hex shorthand */
    color: #F00;  /* Same as #FF0000 */
    
    /* 8-digit hex with alpha */
    color: #FF0000FF;  /* Fully opaque red */
    /* Last FF = Alpha (opacity) */
}
```

3. RGB/RGBA Colors:
```css
.text {
    /* RGB format */
    color: rgb(255, 0, 0);  /* Red */
    /* Explanation:
       255 = Red (0-255)
       0   = Green (0-255)
       0   = Blue (0-255)
    */
    
    /* RGBA with opacity */
    color: rgba(255, 0, 0, 0.5);
    /* Last value (0.5) = 50% opacity */
    
    /* Modern RGB with alpha */
    color: rgb(255 0 0 / 50%);  /* Same as above */
}
```

4. HSL/HSLA Colors:
```css
.text {
    /* HSL format */
    color: hsl(0, 100%, 50%);  /* Red */
    /* Explanation:
       0    = Hue (0-360 degrees)
       100% = Saturation (0-100%)
       50%  = Lightness (0-100%)
    */
    
    /* HSLA with opacity */
    color: hsla(0, 100%, 50%, 0.5);
    /* Last value (0.5) = 50% opacity */
    
    /* Modern HSL with alpha */
    color: hsl(0 100% 50% / 50%);  /* Same as above */
}
```

### Color Variables (Custom Properties):
```css
:root {
    /* Define color variables */
    --primary-color: #007bff;
    --text-dark: #333333;
    --text-light: #666666;
}

.text {
    /* Using color variables */
    color: var(--primary-color);
    
    /* With fallback */
    color: var(--undefined-color, #000);
    /* Uses black if variable not defined */
}
```

### Color Functions:
```css
.text {
    /* RGB function */
    color: rgb(from var(--primary-color) r g b);
    
    /* Lightness adjustments */
    color: color-mix(in srgb, var(--primary-color) 50%, white);
    /* Mixes color with white for lighter shade */
}
```
