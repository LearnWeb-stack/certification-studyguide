# Comprehensive HTML Elements Study Guide

## 1. Table Elements Deep Dive

### Basic Table Structure
Tables consist of four main elements:
- `<table>`: Container element
- `<tr>`: Table row
- `<th>`: Table header cell
- `<td>`: Table data cell

### Table Element Attributes

1. Basic Attributes:
```html
<table 
    border="1"           <!-- Sets border width -->
    cellpadding="10"     <!-- Space inside cells -->
    cellspacing="5"      <!-- Space between cells -->
    width="100%"         <!-- Table width -->
    align="center"       <!-- Table alignment -->
>
```

2. Advanced Table Structure:
```html
<table>
    <caption>Table Title</caption>  <!-- Table caption -->
    <colgroup>                      <!-- Column grouping -->
        <col span="2" style="background-color: #f0f0f0">
        <col style="background-color: #e0e0e0">
    </colgroup>
    <thead>                         <!-- Table header section -->
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
    </thead>
    <tbody>                         <!-- Table body section -->
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
        </tr>
    </tbody>
    <tfoot>                         <!-- Table footer section -->
        <tr>
            <td colspan="2">Footer Data</td>
        </tr>
    </tfoot>
</table>
```

### Complex Table Examples

1. Schedule Table:
```html
<table border="1">
    <caption>Weekly Schedule</caption>
    <thead>
        <tr>
            <th></th>
            <th>Monday</th>
            <th>Tuesday</th>
            <th>Wednesday</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th>Morning</th>
            <td rowspan="2">Team Meeting</td>
            <td>Client Call</td>
            <td>Development</td>
        </tr>
        <tr>
            <th>Afternoon</th>
            <!-- rowspan from above -->
            <td>Training</td>
            <td>Project Work</td>
        </tr>
    </tbody>
</table>
```

2. Data Table with Colspan:
```html
<table border="1">
    <thead>
        <tr>
            <th colspan="4">Quarterly Sales Report</th>
        </tr>
        <tr>
            <th>Product</th>
            <th>Q1</th>
            <th>Q2</th>
            <th>Total</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Product A</td>
            <td>$1,000</td>
            <td>$1,200</td>
            <td>$2,200</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="3">Total Sales</td>
            <td>$2,200</td>
        </tr>
    </tfoot>
</table>
```

### Table CSS Styling
```css
/* Basic table styling */
table {
    border-collapse: collapse;
    width: 100%;
    margin: 20px 0;
}

th, td {
    padding: 12px;
    text-align: left;
    border: 1px solid #ddd;
}

/* Zebra striping */
tbody tr:nth-child(even) {
    background-color: #f2f2f2;
}

/* Hover effect */
tbody tr:hover {
    background-color: #ddd;
}

/* Header styling */
th {
    background-color: #4CAF50;
    color: white;
}
```

## 2. Headings (h1-h6) In-Depth

### Semantic Usage and Hierarchy
```html
<article>
    <h1>Main Article Title</h1>  <!-- Primary heading -->
    
    <section>
        <h2>Major Section</h2>   <!-- Section heading -->
        
        <h3>Subsection</h3>      <!-- Subsection heading -->
        <p>Content...</p>
        
        <h3>Another Subsection</h3>
        <h4>Detailed Point</h4>   <!-- Further subdivision -->
        
        <h5>Minor Section</h5>    <!-- Rare usage -->
        <h6>Finest Detail</h6>    <!-- Very rare usage -->
    </section>
</article>
```

### Heading Best Practices

1. Document Outline:
```html
<!-- Good Practice -->
<h1>Website Title</h1>
<h2>Main Section</h2>
<h3>Subsection</h3>

<!-- Bad Practice - Skipping Levels -->
<h1>Website Title</h1>
<h3>Subsection</h3>  <!-- Skipped h2 -->
```

2. Multiple Page Sections:
```html
<main>
    <h1>Main Content Title</h1>
    
    <section>
        <h2>Section One</h2>
        <p>Content...</p>
    </section>
    
    <section>
        <h2>Section Two</h2>
        <h3>Subsection 2.1</h3>
        <p>Content...</p>
    </section>
</main>

<aside>
    <h2>Related Content</h2>
    <p>Sidebar content...</p>
</aside>
```

### Heading Styling
```css
/* Base heading styles */
h1, h2, h3, h4, h5, h6 {
    font-family: 'Arial', sans-serif;
    line-height: 1.2;
    margin-top: 1em;
    margin-bottom: 0.5em;
}

/* Individual heading sizes */
h1 {
    font-size: 2.5em;
    color: #333;
}

h2 {
    font-size: 2em;
    color: #444;
}

h3 {
    font-size: 1.75em;
    color: #555;
}

h4 {
    font-size: 1.5em;
    color: #666;
}

h5 {
    font-size: 1.25em;
    color: #777;
}

h6 {
    font-size: 1em;
    color: #888;
}
```

## 3. Paragraph and Text Elements

### Paragraph Elements
```html
<!-- Basic paragraph -->
<p>This is a simple paragraph of text.</p>

<!-- Paragraph with formatting -->
<p>
    This paragraph contains <strong>bold text</strong>,
    <em>italic text</em>, and <mark>highlighted text</mark>.
    It can also include <sub>subscript</sub> and
    <sup>superscript</sup> text.
</p>

<!-- Paragraph with alignment -->
<p style="text-align: center">
    This paragraph is centered on the page.
</p>

<!-- Paragraph with line breaks -->
<p>
    Line one<br>
    Line two<br>
    Line three
</p>
```

### Break and Horizontal Rule Elements

1. Line Break (br):
```html
<!-- Poetry example -->
<p>
    Roses are red<br>
    Violets are blue<br>
    Sugar is sweet<br>
    And so are you
</p>

<!-- Address example -->
<address>
    John Smith<br>
    123 Main Street<br>
    City, State 12345
</address>
```

2. Horizontal Rule (hr):
```html
<h2>Section 1</h2>
<p>Content for section 1...</p>

<hr>  <!-- Standard horizontal rule -->

<h2>Section 2</h2>
<p>Content for section 2...</p>

<!-- Styled horizontal rule -->
<hr style="
    height: 2px;
    background-color: #333;
    border: none;
    margin: 20px 0;
">
```

## 4. Container Elements (div and span)

### Division Element (div)

1. Basic Structure:
```html
<div class="container">
    <h2>Section Title</h2>
    <p>Section content...</p>
</div>
```

2. Nested Divisions:
```html
<div class="outer-container">
    <div class="header">
        <h1>Page Title</h1>
    </div>
    
    <div class="content">
        <div class="article">
            <h2>Article Title</h2>
            <p>Article content...</p>
        </div>
        
        <div class="sidebar">
            <h3>Related Links</h3>
            <ul>
                <li>Link 1</li>
                <li>Link 2</li>
            </ul>
        </div>
    </div>
    
    <div class="footer">
        <p>Footer content...</p>
    </div>
</div>
```

### Span Element

1. Text Formatting:
```html
<p>
    This text contains a <span class="highlight">highlighted</span> word
    and a <span class="emphasize">emphasized</span> phrase.
</p>
```

2. Multiple Spans:
```html
<p>
    Contact us at 
    <span class="phone">(555) 123-4567</span> or
    <span class="email">email@example.com</span>
</p>
```

### CSS for Containers
```css
/* Division styling */
.container {
    width: 80%;
    margin: 0 auto;
    padding: 20px;
    background-color: #f9f9f9;
}

.header {
    background-color: #333;
    color: white;
    padding: 10px;
    margin-bottom: 20px;
}

/* Span styling */
.highlight {
    background-color: yellow;
    padding: 2px 5px;
}

.emphasize {
    font-weight: bold;
    color: red;
}
```

## 5. Lists (Ordered, Unordered, and List Items)

### Unordered Lists

1. Basic Unordered List:
```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

2. Nested Unordered Lists:
```html
<ul>
    <li>Main item 1
        <ul>
            <li>Sub item 1.1</li>
            <li>Sub item 1.2</li>
        </ul>
    </li>
    <li>Main item 2
        <ul>
            <li>Sub item 2.1</li>
            <li>Sub item 2.2</li>
        </ul>
    </li>
</ul>
```

### Ordered Lists

1. Basic Ordered List:
```html
<ol>
    <li>First step</li>
    <li>Second step</li>
    <li>Third step</li>
</ol>
```

2. Custom Numbered Lists:
```html
<!-- Alphabetical list -->
<ol type="A">
    <li>Item A</li>
    <li>Item B</li>
    <li>Item C</li>
</ol>

<!-- Roman numerals -->
<ol type="I">
    <li>Section I</li>
    <li>Section II</li>
    <li>Section III</li>
</ol>

<!-- Start from specific number -->
<ol start="5">
    <li>Fifth item</li>
    <li>Sixth item</li>
    <li>Seventh item</li>
</ol>
```

3. Complex List Structures:
```html
<ol>
    <li>Main step
        <ul>
            <li>Sub point</li>
            <li>Another sub point
                <ol type="a">
                    <li>Detailed step a</li>
                    <li>Detailed step b</li>
                </ol>
            </li>
        </ul>
    </li>
    <li>Next main step</li>
</ol>
```

### List Styling
```css
/* Basic list styling */
ul, ol {
    margin: 1em 0;
    padding-left: 40px;
}

/* Custom bullet points */
ul {
    list-style-type: square;
}

/* Nested list styling */
ul ul {
    list-style-type: circle;
}

/* Ordered list variations */
ol {
    list-style-type: decimal;
}

ol ol {
    list-style-type: lower-alpha;
}

/* List item spacing */
li {
    margin-bottom: 0.5em;
}

/* Custom list styling */
.custom-list {
    list-style: none;
    padding: 0;
}

.custom-list li {
    padding-left: 20px;
    position: relative;
}

.custom-list li::before {
    content: "→";
    position: absolute;
    left: 0;
}
```

## Best Practices and Tips

1. Table Best Practices:
- Use tables only for tabular data
- Include proper headers
- Use caption for table description
- Consider responsive design
- Use semantic markup (thead, tbody, tfoot)

2. Heading Guidelines:
- One h1 per page
- Follow hierarchical order
- Use descriptive text
- Keep headings concise
- Consider SEO impact

3. Paragraph Usage:
- Use for text content
- Keep paragraphs focused
- Use appropriate spacing
- Include proper formatting

4. Container Usage:
- Use semantic elements when possible
- Keep nesting reasonable
- Use classes for styling
- Consider document structure

5. List Guidelines:
- Choose appropriate list type
- Use semantic meaning
- Maintain consistent structure
- Consider nested lists carefully

## Accessibility Considerations

1. Tables:
```html
<!-- Accessible table structure -->
<table>
    <caption>Monthly Sales Data</caption>
    <thead>
        <tr>
            <th scope="col">Month</th>
            <th scope="col">Sales</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">January</th>
            <td>$1,000</td>
        </tr>
    </tbody>
</table>
```

2. Headings:
```html
<!-- Proper heading structure -->
<main>
    <h1>Primary Page Title</h1>
    <article>
        <h2>Article Title</h2>
        <section>
            <h3>Section Title</h3>
        </section>
    </article>
</main>
```

3. Lists:
```html
<!-- Accessible list structure -->
<nav>
    <h2>Navigation</h2>
    <ul role="navigation">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
    </ul>
</nav>
```
