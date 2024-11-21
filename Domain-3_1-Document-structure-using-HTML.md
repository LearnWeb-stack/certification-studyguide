# HTML Elements Study Guide

## 1. Table Elements (table, tr, th, td)

### Purpose:
- Create structured tabular data
- Organize information in rows and columns
- Present data in a grid format

### Elements:
- `<table>`: Container for tabular data
- `<tr>`: Table row
- `<th>`: Table header cell
- `<td>`: Table data cell

### Basic Table Structure:
```html
<table border="1">
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

### Advanced Table Examples:

1. Table with Column and Row Headers:
```html
<table border="1">
    <tr>
        <th></th>
        <th>Monday</th>
        <th>Tuesday</th>
    </tr>
    <tr>
        <th>Morning</th>
        <td>Math</td>
        <td>English</td>
    </tr>
    <tr>
        <th>Afternoon</th>
        <td>Science</td>
        <td>History</td>
    </tr>
</table>
```

2. Table with Colspan and Rowspan:
```html
<table border="1">
    <tr>
        <th colspan="2">Combined Header</th>
    </tr>
    <tr>
        <td rowspan="2">Row 1-2</td>
        <td>Row 1</td>
    </tr>
    <tr>
        <td>Row 2</td>
    </tr>
</table>
```

3. Table with Caption and Sections:
```html
<table border="1">
    <caption>Class Schedule</caption>
    <thead>
        <tr>
            <th>Time</th>
            <th>Subject</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>9:00 AM</td>
            <td>Mathematics</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2">Schedule may change</td>
        </tr>
    </tfoot>
</table>
```

## 2. Heading Elements (h1-h6)

### Purpose:
- Define document structure
- Create hierarchy of content
- Improve SEO and accessibility

### Usage Examples:
```html
<h1>Main Title</h1>
<h2>Section Heading</h2>
<h3>Sub-section</h3>
<h4>Sub-sub-section</h4>
<h5>Small heading</h5>
<h6>Smallest heading</h6>
```

### Proper Heading Hierarchy:
```html
<h1>Website Title</h1>
<section>
    <h2>Main Section</h2>
    <article>
        <h3>Article Title</h3>
        <h4>Article Subsection</h4>
    </article>
</section>
```

## 3. Paragraph Element (p)

### Purpose:
- Define paragraphs of text
- Create text blocks
- Maintain proper spacing

### Examples:

1. Basic Paragraph:
```html
<p>This is a simple paragraph of text.</p>
```

2. Multiple Paragraphs:
```html
<p>First paragraph with some text.</p>
<p>Second paragraph with different text.</p>
```

3. Paragraph with Formatting:
```html
<p>This paragraph contains <strong>bold</strong> and <em>italic</em> text.</p>
```

## 4. Line Break (br) and Horizontal Rule (hr)

### Purpose:
- br: Create line breaks within text
- hr: Create horizontal dividing lines

### Examples:

1. Line Breaks:
```html
<p>Line 1<br>
Line 2<br>
Line 3</p>
```

2. Horizontal Rules:
```html
<h2>Section 1</h2>
<p>Content for section 1</p>
<hr>
<h2>Section 2</h2>
<p>Content for section 2</p>
```

## 5. Division and Span Elements (div, span)

### Purpose:
- div: Block-level container
- span: Inline container

### Examples:

1. Basic Div Usage:
```html
<div class="container">
    <h2>Section Title</h2>
    <p>Section content</p>
</div>
```

2. Nested Divs:
```html
<div class="outer">
    <div class="inner">
        <p>Nested content</p>
    </div>
</div>
```

3. Span Usage:
```html
<p>This is a <span class="highlight">highlighted</span> word.</p>
```

## 6. Lists (ul, ol, li)

### Purpose:
- ul: Unordered list
- ol: Ordered list
- li: List item

### Examples:

1. Unordered List:
```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

2. Ordered List:
```html
<ol>
    <li>First step</li>
    <li>Second step</li>
    <li>Third step</li>
</ol>
```

3. Nested Lists:
```html
<ul>
    <li>Main item 1
        <ul>
            <li>Sub item 1</li>
            <li>Sub item 2</li>
        </ul>
    </li>
    <li>Main item 2</li>
</ul>
```

4. Custom Ordered List:
```html
<ol type="A">
    <li>Option A</li>
    <li>Option B</li>
    <li>Option C</li>
</ol>
```

## Advanced Examples and Combinations

### 1. Complete Content Section:
```html
<div class="section">
    <h2>Section Title</h2>
    <p>Introductory paragraph with <span class="highlight">highlighted</span> text.</p>
    
    <h3>Subsection</h3>
    <ul>
        <li>Point 1</li>
        <li>Point 2</li>
    </ul>
    
    <hr>
    
    <table border="1">
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
        </tr>
    </table>
</div>
```

### 2. Article Structure:
```html
<article>
    <h1>Main Article Title</h1>
    
    <div class="author-info">
        <span class="author">John Doe</span>
        <span class="date">2024-01-01</span>
    </div>
    
    <p>Introduction paragraph...</p>
    
    <h2>First Section</h2>
    <p>Section content...</p>
    
    <h3>Subsection</h3>
    <ul>
        <li>Key point 1</li>
        <li>Key point 2</li>
    </ul>
    
    <table class="data-table">
        <tr>
            <th>Category</th>
            <th>Value</th>
        </tr>
        <tr>
            <td>Item 1</td>
            <td>100</td>
        </tr>
    </table>
</article>
```

## Best Practices

1. Tables:
- Use tables only for tabular data
- Include proper headers (th)
- Use caption when appropriate
- Consider responsive design

2. Headings:
- Maintain proper hierarchy (h1 to h6)
- Don't skip heading levels
- Use only one h1 per page
- Keep headings descriptive

3. Paragraphs:
- Use for text content
- Keep paragraphs focused
- Use proper spacing
- Avoid empty paragraphs

4. Breaks and Rules:
- Use br sparingly
- Prefer CSS for spacing
- Use hr for thematic breaks
- Consider semantic alternatives

5. Containers:
- Use div for logical grouping
- Use span for inline styling
- Keep nesting reasonable
- Use semantic elements when possible

6. Lists:
- Choose appropriate list type
- Maintain consistent structure
- Use proper nesting
- Consider semantic meaning

## Accessibility Considerations

1. Tables:
```html
<table>
    <caption>Monthly Sales</caption>
    <th scope="col">Month</th>
    <th scope="col">Sales</th>
</table>
```

2. Headings:
- Use for document structure
- Maintain proper hierarchy
- Include descriptive text

3. Lists:
- Use appropriate list type
- Include proper context
- Maintain logical structure

## Common Styling Examples

1. CSS with Tables:
```css
table {
    border-collapse: collapse;
    width: 100%;
}

th, td {
    padding: 8px;
    border: 1px solid #ddd;
}

th {
    background-color: #f4f4f4;
}
```

2. CSS with Headings:
```css
h1 {
    font-size: 2.5em;
    color: #333;
}

h2 {
    font-size: 2em;
    color: #666;
}
```

3. CSS with Lists:
```css
ul {
    list-style-type: circle;
    padding-left: 20px;
}

ol {
    list-style-type: decimal;
    padding-left: 20px;
}
```
