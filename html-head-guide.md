# HTML Head Elements Study Guide

## 1. Script Tag
The `<script>` tag is used to embed or reference executable code, typically JavaScript.

### Attributes:
- `src`: External script source
- `type`: Script type
- `defer`: Defers execution until document is parsed
- `async`: Loads script asynchronously
- `integrity`: Subresource integrity check
- `crossorigin`: CORS settings

### Use Cases:

1. External JavaScript File:
```html
<script src="app.js"></script>
```

2. Inline JavaScript:
```html
<script>
    function greetUser() {
        alert("Welcome to our website!");
    }
</script>
```

3. Module Script:
```html
<script type="module" src="modules/main.js"></script>
```

4. Deferred Loading:
```html
<script defer src="heavy-script.js"></script>
```

5. Async Loading:
```html
<script async src="analytics.js"></script>
```

## 2. NoScript Tag
The `<noscript>` tag defines content to be displayed when JavaScript is disabled or not supported.

### Use Cases:

1. Basic Warning Message:
```html
<noscript>
    <p>Please enable JavaScript to use this website.</p>
</noscript>
```

2. Alternative Content:
```html
<noscript>
    <div class="no-js-content">
        <h2>JavaScript Required</h2>
        <p>This website requires JavaScript to function properly.</p>
        <p>Please enable JavaScript in your browser settings.</p>
    </div>
</noscript>
```

3. Fallback Navigation:
```html
<noscript>
    <nav class="static-nav">
        <a href="/home">Home</a>
        <a href="/about">About</a>
        <a href="/contact">Contact</a>
    </nav>
</noscript>
```

## 3. Style Tag
The `<style>` tag is used to define CSS styling information for a document.

### Attributes:
- `type`: Style type (default is "text/css")
- `media`: Media query

### Use Cases:

1. Basic Styling:
```html
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 20px;
    }
    .header {
        background-color: #f0f0f0;
        padding: 10px;
    }
</style>
```

2. Media-Specific Styles:
```html
<style media="screen">
    /* Styles for screen display */
    body { background: white; }
</style>
<style media="print">
    /* Styles for printing */
    body { background: none; }
</style>
```

3. Scoped Styles (Note: Limited browser support):
```html
<style>
    /* Styles specific to a component */
    .component {
        --primary-color: #007bff;
        color: var(--primary-color);
    }
</style>
```

## 4. Link Tag
The `<link>` tag defines relationships between the current document and external resources.

### Attributes:
- `rel`: Relationship type
- `href`: Resource URL
- `type`: Resource type
- `media`: Media query
- `sizes`: Icon sizes
- `crossorigin`: CORS settings

### Use Cases:

1. External Stylesheet:
```html
<link rel="stylesheet" href="styles.css">
```

2. Favicon:
```html
<link rel="icon" type="image/x-icon" href="favicon.ico">
<link rel="apple-touch-icon" sizes="180x180" href="apple-touch-icon.png">
```

3. Alternate Stylesheets:
```html
<link rel="alternate stylesheet" href="dark-theme.css" title="Dark">
<link rel="alternate stylesheet" href="light-theme.css" title="Light">
```

4. Preload Resources:
```html
<link rel="preload" href="important-font.woff2" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="hero-image.jpg" as="image">
```

5. DNS Prefetch:
```html
<link rel="dns-prefetch" href="//api.example.com">
```

## 5. Meta Tags
Meta tags provide metadata about the HTML document.

### 1. Encoding Meta Tag
Specifies character encoding for the document:
```html
<meta charset="UTF-8">
```

### 2. Keywords Meta Tag
Defines keywords for search engines:
```html
<meta name="keywords" content="HTML, CSS, JavaScript, web development, tutorial">
```

### 3. Viewport Meta Tag
Controls viewport behavior on mobile devices:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Additional viewport options:
```html
<!-- Prevent scaling -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">

<!-- Set maximum/minimum scale -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=2.0, minimum-scale=0.5">
```

### 4. Description Meta Tag
Provides a description for search engines:
```html
<meta name="description" content="Learn web development with our comprehensive tutorials covering HTML, CSS, JavaScript, and more.">
```

### Additional Important Meta Tags:

1. Social Media Meta Tags:
```html
<!-- Open Graph (Facebook) -->
<meta property="og:title" content="Page Title">
<meta property="og:description" content="Page description">
<meta property="og:image" content="image.jpg">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Page Title">
<meta name="twitter:description" content="Page description">
```

2. Robot Control:
```html
<meta name="robots" content="index, follow">
<meta name="robots" content="noindex, nofollow">
```

3. Page Refresh/Redirect:
```html
<!-- Refresh page every 30 seconds -->
<meta http-equiv="refresh" content="30">

<!-- Redirect after 5 seconds -->
<meta http-equiv="refresh" content="5;url=https://example.com">
```

## Complete Head Example
Here's a comprehensive example combining various head elements:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Character Encoding -->
    <meta charset="UTF-8">
    
    <!-- Viewport Settings -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO Meta Tags -->
    <meta name="description" content="Complete web development tutorial site">
    <meta name="keywords" content="HTML, CSS, JavaScript, web development">
    <meta name="author" content="John Doe">
    
    <!-- Social Media Tags -->
    <meta property="og:title" content="Web Development Tutorials">
    <meta property="og:description" content="Learn web development">
    <meta property="og:image" content="thumbnail.jpg">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="favicon.ico">
    
    <!-- Stylesheets -->
    <link rel="stylesheet" href="styles.css">
    <style>
        /* Critical CSS */
        .header {
            background-color: #f0f0f0;
        }
    </style>
    
    <!-- Preload Important Resources -->
    <link rel="preload" href="main-font.woff2" as="font" type="font/woff2" crossorigin>
    
    <!-- Scripts -->
    <script defer src="app.js"></script>
    <script>
        // Inline critical JavaScript
        window.addEventListener('load', () => {
            console.log('Page loaded');
        });
    </script>
    
    <!-- Fallback for No JavaScript -->
    <noscript>
        <p>Please enable JavaScript to use this website.</p>
    </noscript>
</head>
<body>
    <!-- Page content -->
</body>
</html>
```

## Best Practices:

1. Meta Tags:
- Always include charset and viewport meta tags
- Use relevant descriptions and keywords
- Keep descriptions under 160 characters

2. Scripts:
- Use defer for non-critical scripts
- Place render-blocking scripts at the end of body
- Use async for independent scripts

3. Styles:
- Link critical CSS in the head
- Use media queries when appropriate
- Consider preloading important styles

4. Performance:
- Minimize the number of files
- Use preload for critical resources
- Implement proper caching strategies

5. SEO:
- Include all relevant meta tags
- Use proper social media tags
- Ensure proper character encoding
