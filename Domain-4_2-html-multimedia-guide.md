# HTML Multimedia and Embedded Elements Guide

## 1. Video Element

### Basic Syntax:
```html
<video src="video.mp4"></video>
```

### Complete Video Element with All Attributes:
```html
<video 
    src="video.mp4"                <!-- Video source -->
    width="1280"                   <!-- Width in pixels -->
    height="720"                   <!-- Height in pixels -->
    controls                       <!-- Show video controls -->
    autoplay                       <!-- Auto-start playback -->
    muted                          <!-- Start muted -->
    loop                          <!-- Loop the video -->
    poster="thumbnail.jpg"        <!-- Thumbnail image -->
    preload="auto"                <!-- Preload behavior -->
    playsinline                   <!-- iOS inline playback -->
    crossorigin="anonymous"       <!-- CORS setting -->
>
    Your browser doesn't support video.
</video>
```

### Video with Multiple Sources:
```html
<video 
    controls 
    width="1280" 
    height="720"
    poster="thumbnail.jpg"
>
    <source 
        src="video.webm" 
        type="video/webm"
    >
    <source 
        src="video.mp4" 
        type="video/mp4"
    >
    <source 
        src="video.ogv" 
        type="video/ogg"
    >
    <p>
        Your browser doesn't support HTML5 video. 
        <a href="video.mp4">Download the video</a>.
    </p>
</video>
```

### Video with Tracks (Subtitles/Captions):
```html
<video controls width="1280" height="720">
    <source src="movie.mp4" type="video/mp4">
    
    <!-- Subtitles -->
    <track 
        kind="subtitles"
        src="subtitles-en.vtt"
        srclang="en"
        label="English"
        default
    >
    
    <!-- Captions -->
    <track 
        kind="captions"
        src="captions-es.vtt"
        srclang="es"
        label="Spanish"
    >
    
    <!-- Chapters -->
    <track 
        kind="chapters"
        src="chapters.vtt"
        srclang="en"
        label="Chapters"
    >
</video>
```

### Advanced Video Examples:

1. Responsive Video:
```html
<div class="video-container">
    <video 
        controls
        width="100%"
        height="auto"
        poster="thumbnail.jpg"
    >
        <source src="video.mp4" type="video/mp4">
        <source src="video.webm" type="video/webm">
    </video>
</div>

<style>
.video-container {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 aspect ratio */
    height: 0;
    overflow: hidden;
}

.video-container video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>
```

2. Video with Picture-in-Picture:
```html
<video 
    id="myVideo"
    controls
    disablePictureInPicture
>
    <source src="video.mp4" type="video/mp4">
</video>
```

## 2. Audio Element

### Basic Syntax:
```html
<audio src="audio.mp3"></audio>
```

### Complete Audio Element with All Attributes:
```html
<audio 
    src="audio.mp3"               <!-- Audio source -->
    controls                      <!-- Show audio controls -->
    autoplay                      <!-- Auto-start playback -->
    muted                         <!-- Start muted -->
    loop                          <!-- Loop the audio -->
    preload="auto"                <!-- Preload behavior -->
    volume="0.8"                  <!-- Initial volume -->
    crossorigin="anonymous"       <!-- CORS setting -->
>
    Your browser doesn't support audio.
</audio>
```

### Audio with Multiple Sources:
```html
<audio controls>
    <source 
        src="audio.ogg" 
        type="audio/ogg"
    >
    <source 
        src="audio.mp3" 
        type="audio/mpeg"
    >
    <source 
        src="audio.wav" 
        type="audio/wav"
    >
    <p>
        Your browser doesn't support HTML5 audio. 
        <a href="audio.mp3">Download the audio</a>.
    </p>
</audio>
```

### Audio Playlist:
```html
<div class="audio-playlist">
    <audio id="audio-player" controls>
        <source src="track1.mp3" type="audio/mpeg">
    </audio>
    
    <ul class="playlist">
        <li data-src="track1.mp3">Track 1</li>
        <li data-src="track2.mp3">Track 2</li>
        <li data-src="track3.mp3">Track 3</li>
    </ul>
</div>
```

## 3. Track Element

### Purpose:
- Add text tracks to media
- Support subtitles, captions, descriptions
- Provide chapter navigation

### Track Types and Examples:

1. Subtitles Track:
```html
<track 
    kind="subtitles"
    src="subs-en.vtt"
    srclang="en"
    label="English Subtitles"
    default
>
```

2. Captions Track:
```html
<track 
    kind="captions"
    src="captions.vtt"
    srclang="en"
    label="English Captions"
>
```

3. Chapters Track:
```html
<track 
    kind="chapters"
    src="chapters.vtt"
    srclang="en"
    label="Chapters"
>
```

4. Descriptions Track:
```html
<track 
    kind="descriptions"
    src="desc.vtt"
    srclang="en"
    label="Audio Descriptions"
>
```

### WebVTT File Example (subtitles.vtt):
```vtt
WEBVTT

1
00:00:01.000 --> 00:00:04.000
Welcome to our video presentation

2
00:00:04.500 --> 00:00:08.000
Today we'll discuss HTML multimedia elements
```

## 4. Source Element

### Purpose:
- Specify multiple media sources
- Provide format fallbacks
- Define different quality versions

### Examples:

1. Video Sources:
```html
<video controls>
    <source 
        src="video-hd.mp4" 
        type="video/mp4"
        media="(min-width: 1080px)"
    >
    <source 
        src="video-sd.mp4" 
        type="video/mp4"
        media="(min-width: 720px)"
    >
    <source 
        src="video-mobile.mp4" 
        type="video/mp4"
    >
</video>
```

2. Audio Sources:
```html
<audio controls>
    <source 
        src="audio-hi.ogg" 
        type="audio/ogg"
    >
    <source 
        src="audio-mid.mp3" 
        type="audio/mpeg"
    >
    <source 
        src="audio-low.wav" 
        type="audio/wav"
    >
</audio>
```

## 5. IFrame Element

### Basic Syntax:
```html
<iframe src="page.html"></iframe>
```

### Complete IFrame with All Attributes:
```html
<iframe 
    src="page.html"                      <!-- Source URL -->
    width="800"                          <!-- Width in pixels -->
    height="600"                         <!-- Height in pixels -->
    name="frame-name"                    <!-- Frame name -->
    allow="fullscreen; payment"          <!-- Permissions -->
    sandbox="allow-scripts allow-same-origin"  <!-- Security restrictions -->
    loading="lazy"                       <!-- Loading behavior -->
    referrerpolicy="no-referrer"        <!-- Referrer policy -->
    srcdoc="<p>HTML content</p>"        <!-- Inline HTML content -->
></iframe>
```

### Common Use Cases:

1. YouTube Video Embed:
```html
<iframe 
    width="560" 
    height="315"
    src="https://www.youtube.com/embed/VIDEO_ID"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; 
           encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
></iframe>
```

2. Google Maps Embed:
```html
<iframe 
    width="600" 
    height="450"
    style="border:0"
    loading="lazy"
    allowfullscreen
    referrerpolicy="no-referrer-when-downgrade"
    src="https://www.google.com/maps/embed?pb=..."
></iframe>
```

3. Responsive IFrame:
```html
<div class="iframe-container">
    <iframe src="page.html"></iframe>
</div>

<style>
.iframe-container {
    position: relative;
    overflow: hidden;
    width: 100%;
    padding-top: 56.25%; /* 16:9 Aspect Ratio */
}

.iframe-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
}
</style>
```

## Best Practices and Tips

### 1. Accessibility:
```html
<!-- Video with accessibility features -->
<video controls>
    <source src="video.mp4" type="video/mp4">
    <track 
        kind="captions" 
        src="captions.vtt" 
        default
    >
    <track 
        kind="descriptions" 
        src="descriptions.vtt"
    >
    <p>
        Video description for screen readers.
        <a href="transcript.html">Read transcript</a>
    </p>
</video>
```

### 2. Performance:
```html
<!-- Lazy loading iframe -->
<iframe 
    src="content.html"
    loading="lazy"
    width="800"
    height="600"
></iframe>

<!-- Preload video -->
<link 
    rel="preload" 
    href="video.mp4" 
    as="video" 
    type="video/mp4"
>
```

### 3. Security:
```html
<!-- Secure iframe implementation -->
<iframe 
    src="trusted-site.com"
    sandbox="allow-scripts allow-same-origin"
    referrerpolicy="no-referrer"
    allow="fullscreen"
></iframe>
```

### 4. Responsive Design:
```html
<!-- Responsive video container -->
<div class="video-wrapper">
    <video controls>
        <source 
            src="video-hd.mp4" 
            media="(min-width: 1080px)"
        >
        <source 
            src="video-sd.mp4" 
            media="(min-width: 720px)"
        >
    </video>
</div>
```

## Common Mistakes to Avoid

1. Missing Fallback Content:
```html
<!-- Wrong -->
<video src="video.mp4"></video>

<!-- Correct -->
<video src="video.mp4">
    <p>Your browser doesn't support HTML5 video.</p>
</video>
```

2. Incorrect MIME Types:
```html
<!-- Wrong -->
<source src="video.mp4" type="video">

<!-- Correct -->
<source src="video.mp4" type="video/mp4">
```

3. Unsecured Iframes:
```html
<!-- Wrong -->
<iframe src="untrusted-site.com"></iframe>

<!-- Correct -->
<iframe 
    src="untrusted-site.com"
    sandbox="allow-scripts"
    referrerpolicy="no-referrer"
></iframe>
```
