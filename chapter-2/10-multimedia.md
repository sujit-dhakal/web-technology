# Chapter 2: Introduction to HTML - Part 10
## Multimedia Elements (Meta, Audio, Video, Canvas)

### 1. Meta Tags

**What are Meta Tags?**

Meta tags provide **metadata** (information about information) about the HTML document. They don't display on the page but are used by browsers, search engines, and social media.

**Location:** Always placed inside `<head>` section.

---

### 2. Essential Meta Tags

#### a) Character Encoding

```html
<meta charset="UTF-8">
```

**Purpose:** Specifies character encoding (supports all languages and symbols)
**Always include this!**

#### b) Viewport (For Responsive Design)

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

**Purpose:** Makes website responsive on mobile devices
**Essential for modern websites!**

#### c) Description

```html
<meta name="description" content="Learn HTML and CSS on our free tutorial website">
```

**Purpose:** Appears in search engine results (150-160 characters recommended)

#### d) Keywords (Less Important Now)

```html
<meta name="keywords" content="HTML, CSS, JavaScript, web development, tutorial">
```

**Purpose:** Search keywords (mostly ignored by modern search engines)

#### e) Author

```html
<meta name="author" content="Ram Sharma">
```

**Purpose:** Identifies the page author

#### f) Refresh/Redirect

```html
<!-- Refresh page every 30 seconds -->
<meta http-equiv="refresh" content="30">

<!-- Redirect to another page after 5 seconds -->
<meta http-equiv="refresh" content="5;url=https://example.com">
```

---

### 3. Social Media Meta Tags

**Open Graph (Facebook, LinkedIn):**

```html
<meta property="og:title" content="My Amazing Article">
<meta property="og:description" content="Learn about HTML meta tags">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:url" content="https://example.com/article.html">
<meta property="og:type" content="article">
```

**Twitter Cards:**

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="My Amazing Article">
<meta name="twitter:description" content="Learn about HTML meta tags">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

**Complete Example:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Essential Meta Tags -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- SEO Meta Tags -->
    <meta name="description" content="Complete HTML tutorial covering all essential topics for beginners and advanced learners">
    <meta name="keywords" content="HTML, HTML5, web development, tutorial, semantic HTML">
    <meta name="author" content="Tech Blog Nepal">

    <!-- Open Graph (Facebook) -->
    <meta property="og:title" content="Complete HTML Tutorial">
    <meta property="og:description" content="Learn HTML from basics to advanced">
    <meta property="og:image" content="https://example.com/html-tutorial.jpg">
    <meta property="og:url" content="https://example.com/html-tutorial">
    <meta property="og:type" content="website">

    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Complete HTML Tutorial">
    <meta name="twitter:description" content="Learn HTML from basics to advanced">
    <meta name="twitter:image" content="https://example.com/html-tutorial.jpg">

    <!-- Favicon -->
    <link rel="icon" type="image/png" href="favicon.png">

    <title>Complete HTML Tutorial | Tech Blog Nepal</title>
</head>
<body>
    <h1>Welcome to HTML Tutorial</h1>
    <p>Content goes here...</p>
</body>
</html>
```

---

### 4. The `<audio>` Element

**What is the Audio Element?**

Embeds sound content (music, podcasts, sound effects) in web pages.

**Basic Syntax:**

```html
<audio controls>
    <source src="audio-file.mp3" type="audio/mpeg">
    <source src="audio-file.ogg" type="audio/ogg">
    Your browser does not support the audio element.
</audio>
```

**Audio Attributes:**

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `controls` | Shows play/pause buttons | `<audio controls>` |
| `autoplay` | Starts automatically (usually blocked) | `<audio autoplay>` |
| `loop` | Repeats continuously | `<audio loop>` |
| `muted` | Starts muted | `<audio muted>` |
| `preload` | How to load: auto/metadata/none | `<audio preload="auto">` |

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Audio Example</title>
</head>
<body>
    <h1>Music Player</h1>

    <!-- Basic audio player -->
    <h2>Song 1</h2>
    <audio controls>
        <source src="song1.mp3" type="audio/mpeg">
        <source src="song1.ogg" type="audio/ogg">
        Your browser does not support the audio element.
    </audio>

    <!-- Autoplay and looping (muted to avoid browser blocking) -->
    <h2>Background Music</h2>
    <audio controls autoplay loop muted>
        <source src="background-music.mp3" type="audio/mpeg">
    </audio>

    <!-- With custom styling -->
    <h2>Styled Audio Player</h2>
    <audio controls style="width: 100%; max-width: 500px;">
        <source src="podcast.mp3" type="audio/mpeg">
    </audio>
</body>
</html>
```

**Supported Audio Formats:**

| Format | MIME Type | Browser Support |
|--------|-----------|-----------------|
| MP3 | `audio/mpeg` | All modern browsers |
| WAV | `audio/wav` | Most browsers |
| OGG | `audio/ogg` | Firefox, Chrome, Opera |

**Best Practice:** Provide multiple formats for compatibility!

---

### 5. The `<video>` Element

**What is the Video Element?**

Embeds video content in web pages.

**Basic Syntax:**

```html
<video width="640" height="360" controls>
    <source src="video-file.mp4" type="video/mp4">
    <source src="video-file.webm" type="video/webm">
    Your browser does not support the video tag.
</video>
```

**Video Attributes:**

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `controls` | Shows video controls | `<video controls>` |
| `autoplay` | Starts automatically | `<video autoplay>` |
| `loop` | Repeats continuously | `<video loop>` |
| `muted` | Starts muted | `<video muted>` |
| `poster` | Thumbnail before playing | `<video poster="thumb.jpg">` |
| `width` / `height` | Dimensions | `<video width="640">` |
| `preload` | Loading strategy | `<video preload="metadata">` |

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Video Example</title>
    <style>
        video {
            max-width: 100%;
            height: auto;
            margin: 20px 0;
            border: 2px solid #333;
        }
    </style>
</head>
<body>
    <h1>Video Gallery</h1>

    <!-- Basic video player -->
    <h2>Tutorial Video</h2>
    <video width="640" height="360" controls poster="thumbnail.jpg">
        <source src="tutorial.mp4" type="video/mp4">
        <source src="tutorial.webm" type="video/webm">
        Your browser does not support the video tag.
    </video>

    <!-- Autoplay with mute (required by browsers) -->
    <h2>Background Video</h2>
    <video width="100%" autoplay loop muted>
        <source src="background.mp4" type="video/mp4">
    </video>

    <!-- Video with subtitles -->
    <h2>Video with Subtitles</h2>
    <video width="640" height="360" controls>
        <source src="lecture.mp4" type="video/mp4">
        <track src="subtitles-en.vtt" kind="subtitles" srclang="en" label="English">
        <track src="subtitles-ne.vtt" kind="subtitles" srclang="ne" label="Nepali">
    </video>
</body>
</html>
```

**Supported Video Formats:**

| Format | MIME Type | Browser Support |
|--------|-----------|-----------------|
| MP4 | `video/mp4` | All modern browsers |
| WebM | `video/webm` | Chrome, Firefox, Opera |
| OGG | `video/ogg` | Firefox, Chrome, Opera |

**Note:** MP4 (H.264 codec) is the most widely supported format.

---

### 6. Custom Video Player Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Custom Video Player</title>
    <style>
        .video-container {
            max-width: 800px;
            margin: 0 auto;
        }
        video {
            width: 100%;
            background-color: black;
        }
        .controls {
            background-color: #333;
            padding: 10px;
            text-align: center;
        }
        .controls button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="video-container">
        <h1>Custom Video Player</h1>

        <video id="myVideo" poster="poster.jpg">
            <source src="sample-video.mp4" type="video/mp4">
        </video>

        <div class="controls">
            <button onclick="playPause()">Play/Pause</button>
            <button onclick="rewind()">⏪ -10s</button>
            <button onclick="forward()">⏩ +10s</button>
            <button onclick="volumeUp()">🔊 Volume Up</button>
            <button onclick="volumeDown()">🔉 Volume Down</button>
        </div>
    </div>

    <script>
        const video = document.getElementById('myVideo');

        function playPause() {
            if (video.paused) {
                video.play();
            } else {
                video.pause();
            }
        }

        function rewind() {
            video.currentTime -= 10;
        }

        function forward() {
            video.currentTime += 10;
        }

        function volumeUp() {
            if (video.volume < 1) {
                video.volume += 0.1;
            }
        }

        function volumeDown() {
            if (video.volume > 0) {
                video.volume -= 0.1;
            }
        }
    </script>
</body>
</html>
```

---

### 7. The `<canvas>` Element

**What is Canvas?**

A canvas is a container for **drawing graphics** (shapes, images, animations) using JavaScript.

**Basic Syntax:**

```html
<canvas id="myCanvas" width="500" height="300"></canvas>
```

**Note:** Canvas itself displays nothing! You need JavaScript to draw.

**Example 1: Drawing Shapes**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Canvas Drawing</title>
    <style>
        canvas {
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <h1>Canvas Graphics</h1>

    <canvas id="myCanvas" width="600" height="400"></canvas>

    <script>
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');

        // Draw rectangle
        ctx.fillStyle = '#4CAF50';
        ctx.fillRect(50, 50, 200, 100);

        // Draw circle
        ctx.beginPath();
        ctx.arc(400, 100, 50, 0, 2 * Math.PI);
        ctx.fillStyle = '#2196F3';
        ctx.fill();

        // Draw line
        ctx.beginPath();
        ctx.moveTo(50, 200);
        ctx.lineTo(550, 200);
        ctx.strokeStyle = 'red';
        ctx.lineWidth = 3;
        ctx.stroke();

        // Draw text
        ctx.font = '30px Arial';
        ctx.fillStyle = 'black';
        ctx.fillText('Hello Canvas!', 200, 300);
    </script>
</body>
</html>
```

**Example 2: Drawing Nepali Flag**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Nepali Flag Canvas</title>
    <style>
        canvas {
            border: 1px solid black;
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h1 style="text-align: center;">Nepal Flag (Simplified)</h1>

    <canvas id="flag" width="400" height="500"></canvas>

    <script>
        const canvas = document.getElementById('flag');
        const ctx = canvas.getContext('2d');

        // Background
        ctx.fillStyle = '#003893'; // Blue

        // Upper triangle
        ctx.beginPath();
        ctx.moveTo(50, 50);
        ctx.lineTo(350, 200);
        ctx.lineTo(50, 200);
        ctx.closePath();
        ctx.fill();

        // Lower triangle
        ctx.beginPath();
        ctx.moveTo(50, 200);
        ctx.lineTo(350, 400);
        ctx.lineTo(50, 450);
        ctx.closePath();
        ctx.fill();

        // Border (crimson)
        ctx.strokeStyle = '#DC143C';
        ctx.lineWidth = 4;
        ctx.stroke();

        // Text
        ctx.fillStyle = 'black';
        ctx.font = '20px Arial';
        ctx.fillText('🇳🇵 Nepal', 150, 480);
    </script>
</body>
</html>
```

**Example 3: Simple Animation**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Canvas Animation</title>
    <style>
        canvas {
            border: 1px solid black;
            display: block;
            margin: 20px auto;
            background-color: #f0f0f0;
        }
    </style>
</head>
<body>
    <h1 style="text-align: center;">Bouncing Ball Animation</h1>

    <canvas id="animation" width="600" height="400"></canvas>

    <script>
        const canvas = document.getElementById('animation');
        const ctx = canvas.getContext('2d');

        let x = canvas.width / 2;
        let y = canvas.height / 2;
        let dx = 3; // Velocity X
        let dy = 2; // Velocity Y
        const radius = 20;

        function drawBall() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Draw ball
            ctx.beginPath();
            ctx.arc(x, y, radius, 0, Math.PI * 2);
            ctx.fillStyle = '#FF5722';
            ctx.fill();
            ctx.closePath();

            // Bounce off walls
            if (x + dx > canvas.width - radius || x + dx < radius) {
                dx = -dx;
            }
            if (y + dy > canvas.height - radius || y + dy < radius) {
                dy = -dy;
            }

            // Move ball
            x += dx;
            y += dy;

            requestAnimationFrame(drawBall);
        }

        drawBall();
    </script>
</body>
</html>
```

**Canvas Use Cases:**

- Drawing graphics and shapes
- Creating charts and graphs
- Game development
- Image manipulation
- Data visualization
- Animation
- Signature capture

---

### 8. Multimedia Comparison

| Element | Purpose | Requires JS | Use Case |
|---------|---------|-------------|----------|
| `<audio>` | Play sound | No | Music, podcasts, sound effects |
| `<video>` | Play video | No | Tutorials, movies, presentations |
| `<canvas>` | Draw graphics | Yes | Games, charts, animations |

---

### 9. Complete Multimedia Page Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Multimedia demonstration page with audio, video, and canvas">
    <meta property="og:title" content="HTML5 Multimedia Demo">
    <meta property="og:description" content="Learn HTML5 multimedia elements">

    <title>HTML5 Multimedia Demo</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        section {
            background-color: white;
            padding: 20px;
            margin: 20px 0;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        video, audio {
            width: 100%;
            max-width: 100%;
        }
        canvas {
            display: block;
            margin: 20px auto;
            border: 2px solid #333;
        }
    </style>
</head>
<body>
    <header>
        <h1>HTML5 Multimedia Elements Demo</h1>
        <p>Explore audio, video, and canvas capabilities</p>
    </header>

    <main>
        <!-- Audio Section -->
        <section>
            <h2>🎵 Audio Player</h2>
            <p>Listen to our podcast:</p>
            <audio controls>
                <source src="podcast.mp3" type="audio/mpeg">
                <source src="podcast.ogg" type="audio/ogg">
                Your browser does not support the audio element.
            </audio>
        </section>

        <!-- Video Section -->
        <section>
            <h2>🎬 Video Player</h2>
            <p>Watch our HTML tutorial:</p>
            <video controls poster="video-thumbnail.jpg">
                <source src="html-tutorial.mp4" type="video/mp4">
                <source src="html-tutorial.webm" type="video/webm">
                <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English">
                Your browser does not support the video tag.
            </video>
        </section>

        <!-- Canvas Section -->
        <section>
            <h2>🎨 Canvas Graphics</h2>
            <p>Interactive drawing with canvas:</p>
            <canvas id="demoCanvas" width="600" height="300"></canvas>
            <button onclick="changeColor()">Change Colors</button>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Tech Tutorial. All rights reserved.</p>
    </footer>

    <script>
        const canvas = document.getElementById('demoCanvas');
        const ctx = canvas.getContext('2d');

        function drawShapes() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Random colors
            const color1 = '#' + Math.floor(Math.random()*16777215).toString(16);
            const color2 = '#' + Math.floor(Math.random()*16777215).toString(16);
            const color3 = '#' + Math.floor(Math.random()*16777215).toString(16);

            // Rectangle
            ctx.fillStyle = color1;
            ctx.fillRect(50, 50, 150, 100);

            // Circle
            ctx.beginPath();
            ctx.arc(400, 100, 60, 0, 2 * Math.PI);
            ctx.fillStyle = color2;
            ctx.fill();

            // Triangle
            ctx.beginPath();
            ctx.moveTo(250, 200);
            ctx.lineTo(350, 200);
            ctx.lineTo(300, 100);
            ctx.closePath();
            ctx.fillStyle = color3;
            ctx.fill();

            // Text
            ctx.fillStyle = 'black';
            ctx.font = '24px Arial';
            ctx.fillText('HTML5 Canvas!', 200, 270);
        }

        function changeColor() {
            drawShapes();
        }

        // Initial draw
        drawShapes();
    </script>
</body>
</html>
```

---

### Summary

**Key Takeaways:**

✅ **Meta Tags**: Provide metadata for SEO, social media, browsers
✅ **Essential meta**: charset, viewport, description
✅ **Social meta**: Open Graph (Facebook), Twitter Cards
✅ **`<audio>`**: Embed sound (controls, autoplay, loop)
✅ **`<video>`**: Embed video (controls, poster, subtitles)
✅ **`<canvas>`**: Draw graphics with JavaScript
✅ **Multiple formats**: Provide MP3/OGG for audio, MP4/WebM for video
✅ **Accessibility**: Include alternative text and subtitles

**Quick Reference:**

```html
<!-- Meta Tags -->
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Page description">

<!-- Audio -->
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
</audio>

<!-- Video -->
<video width="640" height="360" controls poster="thumb.jpg">
    <source src="video.mp4" type="video/mp4">
</video>

<!-- Canvas -->
<canvas id="myCanvas" width="500" height="300"></canvas>
<script>
    const ctx = document.getElementById('myCanvas').getContext('2d');
    ctx.fillRect(10, 10, 100, 50);
</script>
```

**Next Steps:**
Now you understand multimedia elements! Finally, you'll learn about HTML events that make pages interactive!
