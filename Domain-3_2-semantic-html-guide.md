# HTML Semantic Elements Study Guide

## 1. Header Element (`<header>`)

### Purpose:
- Represents introductory content
- Contains navigational aids
- Typically includes heading elements, logos, and navigation

### Syntax and Examples:

1. Basic Header:
```html
<header>
    <h1>Website Title</h1>
    <p>Website tagline or description</p>
</header>
```

2. Header with Navigation:
```html
<header>
    <div class="logo">
        <img src="logo.png" alt="Company Logo">
    </div>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
</header>
```

3. Article Header:
```html
<article>
    <header>
        <h2>Article Title</h2>
        <p class="author">By John Doe</p>
        <p class="published">Published: January 1, 2024</p>
    </header>
    <p>Article content...</p>
</article>
```

## 2. Navigation Element (`<nav>`)

### Purpose:
- Contains major navigation blocks
- Used for site navigation links
- Can be used multiple times in a document

### Syntax and Examples:

1. Basic Navigation:
```html
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#products">Products</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

2. Navigation with Dropdown:
```html
<nav class="main-nav">
    <ul>
        <li><a href="#home">Home</a></li>
        <li class="dropdown">
            <a href="#products">Products</a>
            <ul class="dropdown-content">
                <li><a href="#new">New Arrivals</a></li>
                <li><a href="#featured">Featured</a></li>
                <li><a href="#sale">Sale Items</a></li>
            </ul>
        </li>
    </ul>
</nav>
```

3. Multiple Navigation Sections:
```html
<header>
    <nav class="main-nav">
        <!-- Main navigation -->
    </nav>
</header>

<aside>
    <nav class="sidebar-nav">
        <!-- Secondary navigation -->
    </nav>
</aside>

<footer>
    <nav class="footer-nav">
        <!-- Footer navigation -->
    </nav>
</footer>
```

## 3. Section Element (`<section>`)

### Purpose:
- Represents a standalone section
- Groups related content
- Usually includes a heading

### Syntax and Examples:

1. Basic Section:
```html
<section>
    <h2>Section Title</h2>
    <p>Section content goes here...</p>
</section>
```

2. Multiple Related Sections:
```html
<main>
    <section id="introduction">
        <h2>Introduction</h2>
        <p>Introduction content...</p>
    </section>

    <section id="features">
        <h2>Features</h2>
        <ul>
            <li>Feature 1</li>
            <li>Feature 2</li>
        </ul>
    </section>

    <section id="conclusion">
        <h2>Conclusion</h2>
        <p>Concluding remarks...</p>
    </section>
</main>
```

3. Nested Sections:
```html
<section class="chapter">
    <h2>Chapter 1</h2>
    
    <section class="sub-chapter">
        <h3>1.1 Introduction</h3>
        <p>Content...</p>
    </section>
    
    <section class="sub-chapter">
        <h3>1.2 Main Content</h3>
        <p>Content...</p>
    </section>
</section>
```

## 4. Article Element (`<article>`)

### Purpose:
- Represents a self-contained composition
- Can be independently distributable
- Suitable for syndication

### Syntax and Examples:

1. Basic Article:
```html
<article>
    <h2>Article Title</h2>
    <p>Article content...</p>
</article>
```

2. Blog Post Article:
```html
<article class="blog-post">
    <header>
        <h2>Blog Post Title</h2>
        <p class="meta">
            Posted by <a href="#author">John Doe</a>
            on <time datetime="2024-01-01">January 1, 2024</time>
        </p>
    </header>
    
    <p>Article content...</p>
    
    <footer>
        <p>Tags: <a href="#tag1">Tag1</a>, <a href="#tag2">Tag2</a></p>
    </footer>
</article>
```

3. Nested Articles:
```html
<article class="main-article">
    <h2>Main Article Title</h2>
    <p>Main content...</p>
    
    <section class="comments">
        <h3>Comments</h3>
        <article class="comment">
            <p class="author">User1 says:</p>
            <p>Comment content...</p>
        </article>
        <article class="comment">
            <p class="author">User2 says:</p>
            <p>Comment content...</p>
        </article>
    </section>
</article>
```

## 5. Aside Element (`<aside>`)

### Purpose:
- Contains content tangentially related to surrounding content
- Often used for sidebars
- Can contain related information or advertisements

### Syntax and Examples:

1. Basic Aside:
```html
<aside>
    <h3>Related Links</h3>
    <ul>
        <li><a href="#link1">Link 1</a></li>
        <li><a href="#link2">Link 2</a></li>
    </ul>
</aside>
```

2. Article with Aside:
```html
<article>
    <h2>Main Article Title</h2>
    <p>Main content...</p>
    
    <aside class="related-info">
        <h3>Did You Know?</h3>
        <p>Additional interesting facts...</p>
    </aside>
</article>
```

3. Sidebar Aside:
```html
<main>
    <article>
        <h2>Main Content</h2>
        <p>Article content...</p>
    </article>
    
    <aside class="sidebar">
        <section class="widget">
            <h3>Categories</h3>
            <ul>
                <li><a href="#cat1">Category 1</a></li>
                <li><a href="#cat2">Category 2</a></li>
            </ul>
        </section>
        
        <section class="widget">
            <h3>Archives</h3>
            <ul>
                <li><a href="#jan">January</a></li>
                <li><a href="#feb">February</a></li>
            </ul>
        </section>
    </aside>
</main>
```

## 6. Footer Element (`<footer>`)

### Purpose:
- Contains footer information
- Often includes copyright, contact info
- Can contain navigation links

### Syntax and Examples:

1. Basic Footer:
```html
<footer>
    <p>&copy; 2024 Company Name. All rights reserved.</p>
</footer>
```

2. Complex Footer:
```html
<footer>
    <div class="footer-content">
        <div class="company-info">
            <h3>About Us</h3>
            <p>Company description...</p>
        </div>
        
        <div class="contact-info">
            <h3>Contact</h3>
            <address>
                Email: <a href="mailto:info@example.com">info@example.com</a><br>
                Phone: <a href="tel:+1234567890">123-456-7890</a>
            </address>
        </div>
        
        <div class="social-links">
            <h3>Follow Us</h3>
            <ul>
                <li><a href="#facebook">Facebook</a></li>
                <li><a href="#twitter">Twitter</a></li>
                <li><a href="#linkedin">LinkedIn</a></li>
            </ul>
        </div>
    </div>
    
    <div class="footer-bottom">
        <p>&copy; 2024 Company Name. All rights reserved.</p>
        <nav>
            <a href="#privacy">Privacy Policy</a> |
            <a href="#terms">Terms of Service</a>
        </nav>
    </div>
</footer>
```

## 7. Details and Summary Elements

### Purpose:
- Creates an interactive disclosure widget
- Summary provides a visible heading
- Details contains expandable content

### Syntax and Examples:

1. Basic Usage:
```html
<details>
    <summary>Click to expand</summary>
    <p>Hidden content that appears when clicked...</p>
</details>
```

2. FAQ Implementation:
```html
<section class="faq">
    <h2>Frequently Asked Questions</h2>
    
    <details>
        <summary>What is your return policy?</summary>
        <p>Detailed return policy information...</p>
        <ul>
            <li>30-day return window</li>
            <li>Original packaging required</li>
        </ul>
    </details>
    
    <details>
        <summary>How do I track my order?</summary>
        <p>Order tracking information...</p>
    </details>
</section>
```

## 8. Figure and Figcaption Elements

### Purpose:
- Figure represents self-contained content
- Figcaption provides a caption for the figure
- Often used for images, diagrams, code snippets

### Syntax and Examples:

1. Basic Image with Caption:
```html
<figure>
    <img src="image.jpg" alt="Description">
    <figcaption>Image caption text</figcaption>
</figure>
```

2. Multiple Images in Figure:
```html
<figure>
    <img src="image1.jpg" alt="Description 1">
    <img src="image2.jpg" alt="Description 2">
    <figcaption>Collection of related images</figcaption>
</figure>
```

3. Code Example with Caption:
```html
<figure>
    <pre><code>
        function hello() {
            console.log("Hello, World!");
        }
    </code></pre>
    <figcaption>Example of a JavaScript function</figcaption>
</figure>
```

## Best Practices and Tips

1. Semantic Structure:
- Use elements according to their semantic meaning
- Maintain proper hierarchy
- Consider accessibility
- Use appropriate headings

2. Navigation:
- Keep navigation consistent
- Use descriptive links
- Consider mobile navigation
- Include skip links for accessibility

3. Content Organization:
- Use sections for logical grouping
- Apply articles for independent content
- Use asides appropriately
- Structure footers clearly

4. Accessibility:
- Include proper ARIA roles when needed
- Maintain keyboard accessibility
- Provide alternative text
- Use semantic elements appropriately

5. SEO Considerations:
- Use proper heading hierarchy
- Include descriptive content
- Structure content logically
- Use appropriate meta tags
