# HTML Links and Navigation Study Guide

## 1. Anchor Tags (`<a>`) and href Attribute

### Basic Syntax:
```html
<a href="URL">Link Text</a>
```

### Types of Links:

1. External Links:
```html
<a href="https://www.example.com">Visit Example Website</a>
```

2. Internal Links:
```html
<a href="about.html">About Us</a>
```

3. Email Links:
```html
<a href="mailto:contact@example.com">Send Email</a>
```

4. Phone Links:
```html
<a href="tel:+1234567890">Call Us</a>
```

5. File Downloads:
```html
<a href="documents/file.pdf">Download PDF</a>
```

## 2. Target Attribute

### Purpose:
- Controls how the linked content is displayed
- Determines the browsing context

### Target Values:

1. _blank (New Window/Tab):
```html
<a href="https://www.example.com" target="_blank">
    Opens in New Window
</a>
```

2. _self (Same Window/Tab):
```html
<a href="page.html" target="_self">
    Opens in Same Window
</a>
```

3. _parent (Parent Frame):
```html
<a href="page.html" target="_parent">
    Opens in Parent Frame
</a>
```

4. _top (Full Window Body):
```html
<a href="page.html" target="_top">
    Opens in Full Window
</a>
```

5. Named Frame:
```html
<a href="page.html" target="frameName">
    Opens in Named Frame
</a>
```

### Security Best Practice:
```html
<!-- Add rel="noopener noreferrer" for external links -->
<a href="https://example.com" 
   target="_blank" 
   rel="noopener noreferrer">
    Secure External Link
</a>
```

## 3. Bookmarks (Page Anchors)

### Creating Bookmarks:

1. Using ID Attribute:
```html
<!-- Create the bookmark target -->
<h2 id="section1">Section 1</h2>

<!-- Link to the bookmark -->
<a href="#section1">Go to Section 1</a>
```

2. Multiple Bookmarks:
```html
<nav>
    <a href="#intro">Introduction</a>
    <a href="#chapter1">Chapter 1</a>
    <a href="#chapter2">Chapter 2</a>
</nav>

<section id="intro">
    <h2>Introduction</h2>
    <!-- Content -->
</section>

<section id="chapter1">
    <h2>Chapter 1</h2>
    <!-- Content -->
</section>

<section id="chapter2">
    <h2>Chapter 2</h2>
    <!-- Content -->
</section>
```

3. Linking to Bookmarks from Other Pages:
```html
<a href="page.html#section3">
    Go to Section 3 on Another Page
</a>
```

## 4. Relative vs. Absolute Links

### Absolute Links:
- Complete URL path
- Include protocol and domain
```html
<!-- Absolute URL -->
<a href="https://www.example.com/about/contact.html">
    Contact Us
</a>
```

### Relative Links:
- Path relative to current page location
- No protocol or domain needed

1. Same Directory:
```html
<!-- File in same directory -->
<a href="about.html">About</a>
```

2. Child Directory:
```html
<!-- File in subdirectory -->
<a href="pages/contact.html">Contact</a>
```

3. Parent Directory:
```html
<!-- File in parent directory -->
<a href="../index.html">Home</a>
```

4. Multiple Levels:
```html
<!-- Navigate multiple levels -->
<a href="../../images/photo.jpg">View Photo</a>
```

## 5. Navigating Folder Hierarchies

### Project Structure Example:
```
website/
├── index.html
├── about.html
├── css/
│   └── style.css
├── images/
│   ├── logo.png
│   └── photos/
│       └── gallery.jpg
└── pages/
    ├── contact.html
    └── services/
        └── pricing.html
```

### Navigation Examples:

1. From index.html:
```html
<!-- To files in root -->
<a href="about.html">About</a>

<!-- To files in subdirectories -->
<a href="pages/contact.html">Contact</a>
<a href="pages/services/pricing.html">Pricing</a>

<!-- To images -->
<img src="images/logo.png" alt="Logo">
<img src="images/photos/gallery.jpg" alt="Gallery">
```

2. From pages/services/pricing.html:
```html
<!-- Back to root -->
<a href="../../index.html">Home</a>

<!-- To parent directory -->
<a href="../contact.html">Contact</a>

<!-- To images from deep directory -->
<img src="../../images/logo.png" alt="Logo">
```

## 6. Image Maps (`<map>` and `<area>`)

### Purpose:
- Create clickable regions on images
- Define multiple link areas in one image
- Create complex navigation from single image

### Basic Syntax:
```html
<img src="image.jpg" alt="Navigation Map" usemap="#workmap">

<map name="workmap">
    <area shape="shape-type" coords="coordinates" 
          href="link.html" alt="Description">
</map>
```

### Shape Types and Examples:

1. Rectangle:
```html
<img src="office.jpg" alt="Office Layout" usemap="#officemap">

<map name="officemap">
    <area shape="rect" 
          coords="34,44,270,350" 
          href="conference.html" 
          alt="Conference Room">
</map>
```

2. Circle:
```html
<img src="planets.jpg" alt="Solar System" usemap="#planetmap">

<map name="planetmap">
    <area shape="circle" 
          coords="180,139,14" 
          href="earth.html" 
          alt="Earth">
</map>
```

3. Polygon:
```html
<img src="shape.jpg" alt="Complex Shape" usemap="#shapemap">

<map name="shapemap">
    <area shape="poly" 
          coords="140,121,181,116,204,160,204,222,183,270,141,275" 
          href="region.html" 
          alt="Complex Region">
</map>
```

### Complex Image Map Example:
```html
<img src="navigation.jpg" 
     alt="Site Navigation" 
     usemap="#navmap">

<map name="navmap">
    <!-- Rectangle area -->
    <area shape="rect" 
          coords="0,0,100,100" 
          href="home.html" 
          alt="Home">
    
    <!-- Circle area -->
    <area shape="circle" 
          coords="200,200,50" 
          href="about.html" 
          alt="About">
    
    <!-- Polygon area -->
    <area shape="poly" 
          coords="300,0,400,100,300,200,200,100" 
          href="contact.html" 
          alt="Contact">
</map>
```

## Best Practices and Tips

1. Link Best Practices:
- Use descriptive link text
- Avoid "click here" or "read more"
- Consider accessibility
- Check for broken links

2. Target Attribute:
- Use _blank sparingly
- Include security attributes
- Consider user experience
- Warn users of new windows

3. Bookmarks:
- Use descriptive IDs
- Keep IDs unique
- Consider page structure
- Add navigation cues

4. File Organization:
- Use logical folder structure
- Keep paths organized
- Use consistent naming
- Consider URL readability

5. Image Maps:
- Provide alternative navigation
- Use appropriate shapes
- Test coordinate accuracy
- Include alt text

## Common Mistakes to Avoid

1. Link Errors:
```html
<!-- Wrong: No protocol -->
<a href="www.example.com">Wrong</a>

<!-- Correct: Include protocol -->
<a href="https://www.example.com">Correct</a>
```

2. Path Errors:
```html
<!-- Wrong: Incorrect path -->
<a href="./pages/about">Wrong</a>

<!-- Correct: Proper file extension -->
<a href="./pages/about.html">Correct</a>
```

3. Target Usage:
```html
<!-- Wrong: No security attributes -->
<a href="https://example.com" target="_blank">Wrong</a>

<!-- Correct: Include security attributes -->
<a href="https://example.com" 
   target="_blank" 
   rel="noopener noreferrer">Correct</a>
```

4. Image Map Errors:
```html
<!-- Wrong: Mismatched name/id -->
<img src="map.jpg" usemap="#map1">
<map name="map2">  <!-- Different name -->
    <!-- Areas -->
</map>

<!-- Correct: Matching name/id -->
<img src="map.jpg" usemap="#sitemap">
<map name="sitemap">
    <!-- Areas -->
</map>
```
