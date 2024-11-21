# HTML Image Elements and Attributes Guide

## 1. Image (`<img>`) Element

### Basic Syntax:
```html
<img src="path/to/image.jpg" alt="Image description">
```

### Complete Attributes List:

```html
<img 
    src="image.jpg"              <!-- Source path (required) -->
    alt="Description"            <!-- Alternative text (required) -->
    width="800"                  <!-- Width in pixels -->
    height="600"                 <!-- Height in pixels -->
    loading="lazy"               <!-- Loading behavior -->
    decoding="async"            <!-- Image decoding hint -->
    srcset="image-sets"         <!-- Responsive image sources -->
    sizes="size-conditions"     <!-- Size conditions -->
    crossorigin="anonymous"     <!-- CORS settings -->
    ismap                       <!-- Server-side image map -->
    usemap="#mapname"           <!-- Client-side image map -->
    referrerpolicy="origin"     <!-- Referrer policy -->
>
```

### Common Use Cases:

1. Basic Image:
```html
<img src="photo.jpg" alt="A beautiful landscape">
```

2. Sized Image:
```html
<img 
    src="profile.jpg" 
    alt="User profile picture"
    width="200" 
    height="200"
>
```

3. Responsive Image:
```html
<img 
    src="image.jpg"
    alt="Responsive image"
    srcset="small.jpg 300w,
            medium.jpg 600w,
            large.jpg 900w"
    sizes="(max-width: 320px) 280px,
           (max-width: 640px) 580px,
           900px"
>
```

4. Lazy Loading:
```html
<img 
    src="large-image.jpg"
    alt="Lazy loaded image"
    loading="lazy"
    decoding="async"
>
```

### Image Formats and Use Cases:

1. JPEG Format:
```html
<!-- Best for photographs -->
<img 
    src="photo.jpg" 
    alt="Photograph"
    width="800"
    height="600"
>
```

2. PNG Format:
```html
<!-- Best for images with transparency -->
<img 
    src="logo.png" 
    alt="Company logo"
    width="200"
    height="100"
>
```

3. WebP Format:
```html
<!-- Modern format with better compression -->
<img 
    src="image.webp" 
    alt="WebP image"
    width="600"
    height="400"
>
```

4. SVG Format:
```html
<!-- Vector graphics that scale without loss -->
<img 
    src="icon.svg" 
    alt="Scalable icon"
    width="50"
    height="50"
>
```

## 2. Picture Element

### Purpose:
- Provides multiple sources for an image
- Allows art direction
- Supports different formats and resolutions
- Better browser support for responsive images

### Basic Syntax:
```html
<picture>
    <source srcset="image1.jpg">
    <source srcset="image2.jpg">
    <img src="fallback.jpg" alt="Description">
</picture>
```

### Use Cases:

1. Different Image Formats:
```html
<picture>
    <source 
        srcset="image.webp"
        type="image/webp"
    >
    <source 
        srcset="image.jpg"
        type="image/jpeg"
    >
    <img 
        src="image.jpg" 
        alt="Image with format fallback"
    >
</picture>
```

2. Art Direction (Different Crops):
```html
<picture>
    <source 
        media="(min-width: 800px)"
        srcset="landscape.jpg"
    >
    <source 
        media="(min-width: 400px)"
        srcset="square.jpg"
    >
    <img 
        src="portrait.jpg" 
        alt="Responsive image with different crops"
    >
</picture>
```

3. Resolution Switching:
```html
<picture>
    <source 
        media="(min-width: 1200px)"
        srcset="large.jpg 1200w,
                larger.jpg 1800w"
        sizes="80vw"
    >
    <source 
        media="(min-width: 700px)"
        srcset="medium.jpg 700w,
                large.jpg 1200w"
        sizes="70vw"
    >
    <img 
        src="small.jpg" 
        alt="Resolution-dependent image"
        srcset="small.jpg 400w,
                medium.jpg 700w"
        sizes="100vw"
    >
</picture>
```

## 3. Advanced Examples and Best Practices

### 1. Responsive Product Images:
```html
<picture>
    <!-- High-DPI Desktop Screens -->
    <source 
        media="(min-width: 1200px) and (-webkit-min-device-pixel-ratio: 2)"
        srcset="product-xl@2x.webp"
        type="image/webp"
    >
    
    <!-- Desktop Screens -->
    <source 
        media="(min-width: 1200px)"
        srcset="product-xl.webp"
        type="image/webp"
    >
    
    <!-- Tablet Screens -->
    <source 
        media="(min-width: 768px)"
        srcset="product-md.webp"
        type="image/webp"
    >
    
    <!-- Mobile Screens -->
    <source 
        media="(max-width: 767px)"
        srcset="product-sm.webp"
        type="image/webp"
    >
    
    <!-- Fallback -->
    <img 
        src="product-fallback.jpg" 
        alt="Product image"
        loading="lazy"
        width="800"
        height="600"
    >
</picture>
```

### 2. Background Images with Picture:
```html
<picture>
    <source 
        srcset="background-dark.jpg"
        media="(prefers-color-scheme: dark)"
    >
    <source 
        srcset="background-light.jpg"
        media="(prefers-color-scheme: light)"
    >
    <img 
        src="background-default.jpg" 
        alt=""
        role="presentation"
        width="1920"
        height="1080"
    >
</picture>
```

### 3. Accessibility-Enhanced Image:
```html
<figure>
    <picture>
        <source 
            srcset="image-hd.jpg"
            media="(min-width: 800px)"
        >
        <img 
            src="image.jpg" 
            alt="Detailed description of image"
            width="400"
            height="300"
            role="img"
            aria-labelledby="caption"
        >
    </picture>
    <figcaption id="caption">
        Extended description of the image for better context
    </figcaption>
</figure>
```

## 4. Best Practices

### 1. Performance:
```html
<!-- Lazy loading for below-fold images -->
<img 
    src="below-fold.jpg"
    alt="Below fold content"
    loading="lazy"
    decoding="async"
>

<!-- Preload critical images -->
<link 
    rel="preload" 
    as="image" 
    href="hero.jpg"
>
```

### 2. Accessibility:
```html
<!-- Decorative image -->
<img 
    src="decoration.jpg" 
    alt=""
    role="presentation"
>

<!-- Informative image -->
<img 
    src="chart.jpg" 
    alt="Sales chart showing 50% growth in Q2"
    aria-describedby="chart-description"
>
<p id="chart-description">Detailed description of the chart...</p>
```

### 3. Responsive Images:
```html
<!-- Using srcset and sizes -->
<img 
    src="fallback.jpg"
    alt="Responsive image"
    srcset="small.jpg 300w,
            medium.jpg 600w,
            large.jpg 900w"
    sizes="(max-width: 320px) 280px,
           (max-width: 640px) 580px,
           900px"
    loading="lazy"
>
```

### 4. Image Maps:
```html
<img 
    src="map.jpg" 
    alt="Interactive map"
    usemap="#workmap"
>
<map name="workmap">
    <area 
        shape="rect" 
        coords="34,44,270,350" 
        alt="Computer" 
        href="computer.htm"
    >
    <area 
        shape="circle" 
        coords="337,300,44" 
        alt="Coffee" 
        href="coffee.htm"
    >
</map>
```

## Common Mistakes to Avoid

1. Missing Alt Text:
```html
<!-- Wrong -->
<img src="image.jpg">

<!-- Correct -->
<img src="image.jpg" alt="Descriptive text">
```

2. Incorrect Dimensions:
```html
<!-- Wrong -->
<img src="image.jpg" alt="Image">

<!-- Correct -->
<img 
    src="image.jpg" 
    alt="Image"
    width="800"
    height="600"
>
```

3. Non-Responsive Images:
```html
<!-- Wrong -->
<img src="large-image.jpg" alt="Image">

<!-- Correct -->
<picture>
    <source 
        media="(min-width: 800px)"
        srcset="large.jpg"
    >
    <source 
        media="(min-width: 400px)"
        srcset="medium.jpg"
    >
    <img src="small.jpg" alt="Image">
</picture>
```

## Image Optimization Tips

1. Choose the Right Format:
- JPEG: Photos and complex images
- PNG: Images with transparency
- WebP: Modern browsers, better compression
- SVG: Icons and logos

2. Use Appropriate Sizes:
- Don't scale down large images with CSS
- Provide multiple sizes for different devices
- Use srcset for resolution switching

3. Optimize Loading:
- Use lazy loading for non-critical images
- Preload critical images
- Implement progressive loading

4. Consider Accessibility:
- Always provide meaningful alt text
- Use ARIA attributes when needed
- Consider color contrast
- Provide text alternatives for complex images
