# HTML Structure and Syntax Study Guide

## 1. DOCTYPE Declaration

### Purpose:
- Informs the browser about the HTML version being used
- Ensures proper rendering and standard mode
- Required for HTML validation

### Syntax Variations:

1. HTML5 (Modern and Recommended):
```html
<!DOCTYPE html>
```

2. HTML 4.01 Strict:
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

3. HTML 4.01 Transitional:
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

4. XHTML 1.0 Strict:
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

### Important Rules:
- Must be the very first line in the HTML document
- Case-insensitive but conventionally uppercase
- No closing tag needed
- No spaces before the declaration

## 2. HTML Element

### Purpose:
- Root element of an HTML document
- Contains all other HTML elements
- Defines document language and directionality

### Attributes:
1. Language Declaration:
```html
<html lang="en">
```

2. Right-to-Left Text Direction:
```html
<html dir="rtl">
```

3. Multiple Attributes:
```html
<html lang="ar" dir="rtl">
```

### Proper Syntax:
```html
<!DOCTYPE html>
<html lang="en">
    <!-- Document content -->
</html>
```

## 3. Head Element

### Purpose:
- Container for metadata
- Not visible in browser window
- Contains document information

### Required Elements:
```html
<head>
    <meta charset="UTF-8">
    <title>Page Title</title>
</head>
```

### Complete Example:
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Title</title>
    <link rel="stylesheet" href="styles.css">
    <script src="script.js"></script>
</head>
```

## 4. Body Element

### Purpose:
- Contains visible page content
- Holds all displayable content
- Supports event attributes

### Basic Structure:
```html
<body>
    <header>
        <!-- Header content -->
    </header>
    
    <main>
        <!-- Main content -->
    </main>
    
    <footer>
        <!-- Footer content -->
    </footer>
</body>
```

### Event Attributes Example:
```html
<body onload="initPage()" onunload="cleanup()">
    <!-- Page content -->
</body>
```

## 5. Proper HTML Syntax

### Basic Rules:
1. Element Structure:
```html
<tagname attribute="value">content</tagname>
```

2. Self-Closing Elements:
```html
<input type="text">
<img src="image.jpg" alt="description">
<br>
<hr>
```

3. Nested Elements:
```html
<div>
    <p>This is <strong>properly</strong> nested.</p>
</div>
```

### Common Mistakes to Avoid:

1. Incorrect Nesting:
```html
<!-- Wrong -->
<p><strong>Text</p></strong>

<!-- Correct -->
<p><strong>Text</strong></p>
```

2. Missing Closing Tags:
```html
<!-- Wrong -->
<div>
    <p>Content
</div>

<!-- Correct -->
<div>
    <p>Content</p>
</div>
```

3. Mixed Case Tags:
```html
<!-- Not Recommended -->
<DIV>
    <P>Content</P>
</div>

<!-- Recommended -->
<div>
    <p>Content</p>
</div>
```

## 6. Closing Tags

### Elements Requiring Closing Tags:
```html
<p>...</p>
<div>...</div>
<span>...</span>
<h1>...</h1>
<table>...</table>
<form>...</form>
```

### Self-Closing Elements (No Closing Tag):
```html
<img src="image.jpg" alt="description">
<br>
<hr>
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="styles.css">
```

### HTML5 Void Elements:
- area
- base
- br
- col
- embed
- hr
- img
- input
- link
- meta
- param
- source
- track
- wbr

## 7. Commonly Used Symbols & Special Characters

### HTML Entities:
```html
&lt;      <!-- < Less than -->
&gt;      <!-- > Greater than -->
&amp;     <!-- & Ampersand -->
&quot;    <!-- " Double quote -->
&apos;    <!-- ' Single quote -->
&copy;    <!-- © Copyright -->
&reg;     <!-- ® Registered trademark -->
&trade;   <!-- ™ Trademark -->
&nbsp;    <!-- Non-breaking space -->
&euro;    <!-- € Euro -->
&pound;   <!-- £ Pound -->
&cent;    <!-- ¢ Cent -->
&deg;     <!-- ° Degree -->
&plusmn;  <!-- ± Plus-minus -->
&times;   <!-- × Multiplication -->
&divide;  <!-- ÷ Division -->
&frac12;  <!-- ½ Half -->
&frac14;  <!-- ¼ Quarter -->
&frac34;  <!-- ¾ Three quarters -->
```

### Mathematical Symbols:
```html
&sum;     <!-- ∑ Summation -->
&infin;   <!-- ∞ Infinity -->
&radic;   <!-- √ Square root -->
&ge;      <!-- ≥ Greater than or equal -->
&le;      <!-- ≤ Less than or equal -->
&ne;      <!-- ≠ Not equal -->
&equiv;   <!-- ≡ Identical -->
```

### Arrows:
```html
&larr;    <!-- ← Left arrow -->
&rarr;    <!-- → Right arrow -->
&uarr;    <!-- ↑ Up arrow -->
&darr;    <!-- ↓ Down arrow -->
&harr;    <!-- ↔ Left right arrow -->
```

## 8. Complete HTML Document Structure

### Basic Template:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Title</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Website Title</h1>
        <nav>
            <!-- Navigation content -->
        </nav>
    </header>

    <main>
        <article>
            <h2>Article Title</h2>
            <p>Content with <em>emphasis</em> and <strong>strong</strong> text.</p>
        </article>
    </main>

    <footer>
        <p>&copy; 2024 Your Company. All rights reserved.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
```

## 9. Best Practices

1. Document Structure:
- Always include DOCTYPE declaration
- Use proper HTML5 semantic elements
- Include required meta tags

2. Syntax:
- Use lowercase for tags and attributes
- Quote attribute values
- Properly nest elements
- Close all elements that require closing

3. Accessibility:
- Include proper lang attribute
- Use semantic HTML elements
- Provide alternative text for images
- Ensure proper heading hierarchy

4. Validation:
- Regularly validate HTML code
- Fix validation errors
- Use proper document structure

5. Maintenance:
- Use consistent indentation
- Add comments for complex sections
- Keep code organized and clean
- Follow a style guide

## 10. Common Debugging Tools

1. Browser Developer Tools:
- Element inspector
- HTML validation
- Source code viewer

2. Online Validators:
- W3C Markup Validation Service
- HTML5 Validator

3. Code Editors:
- Syntax highlighting
- Auto-completion
- Error detection
- Format document features
