# Chapter 2: Introduction to HTML - Part 7
## Frames

### 1. Introduction to Frames

**What are Frames?**

Frames were an HTML feature that allowed a web page to be divided into multiple independent sections, each displaying a different HTML document.

**Important Note:**
⚠️ **Frames are DEPRECATED and REMOVED from HTML5.**
⚠️ **Do NOT use frames in modern web development.**
⚠️ **This section is for educational purposes only.**

**Real-World Analogy:**

Think of frames like a window with multiple panes - each pane shows a different view, but they're all part of one window.

---

### 2. Why Were Frames Used?

**Historical Use Cases:**

1. **Navigation menu**: Fixed sidebar/top menu that stays while content changes
2. **Split views**: Show two documents side-by-side
3. **Persistent header/footer**: Keep header/footer while scrolling content
4. **Multiple content areas**: Divide page into independent sections

**Example Use (OLD WAY):**

```
┌─────────────────────────────────────┐
│         Header (logo, title)        │ ← Frame 1
├──────────┬──────────────────────────┤
│  Menu    │                          │
│  - Home  │      Main Content        │ ← Frame 3
│  - About │      (changes when       │
│  - Help  │       menu clicked)      │
│          │                          │
└──────────┴──────────────────────────┘
    ↑
  Frame 2
```

---

### 3. Frame Syntax (Deprecated)

**Frameset Structure:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Frameset Example (DEPRECATED)</title>
</head>
<frameset rows="20%, 80%">
    <!-- Top frame -->
    <frame src="header.html" name="header">

    <!-- Bottom frame split into two columns -->
    <frameset cols="25%, 75%">
        <frame src="menu.html" name="menu">
        <frame src="content.html" name="content">
    </frameset>
</frameset>
<!-- No <body> tag in frameset! -->
</html>
```

**Frameset Attributes:**

- `rows="20%, 80%"` - Horizontal split (percentages or pixels)
- `cols="25%, 75%"` - Vertical split
- `<frame src="file.html">` - Individual frame
- `name="framename"` - Frame identifier for targeting

---

### 4. Types of Frames

#### a) Horizontal Frames (Rows)

```html
<frameset rows="100, *">
    <frame src="header.html">
    <frame src="content.html">
</frameset>
```

Visual:
```
┌──────────────┐
│   Header     │ 100px
├──────────────┤
│              │
│   Content    │ Remaining space (*)
│              │
└──────────────┘
```

#### b) Vertical Frames (Columns)

```html
<frameset cols="200, *">
    <frame src="menu.html">
    <frame src="main.html">
</frameset>
```

Visual:
```
┌────┬─────────┐
│    │         │
│Menu│  Main   │
│    │ Content │
│    │         │
└────┴─────────┘
 200px  Rest
```

#### c) Nested Frames

```html
<frameset rows="80, *">
    <frame src="header.html">
    <frameset cols="150, *">
        <frame src="menu.html">
        <frame src="content.html">
    </frameset>
</frameset>
```

Visual:
```
┌──────────────────┐
│     Header       │
├─────┬────────────┤
│Menu │  Content   │
│     │            │
└─────┴────────────┘
```

---

### 5. Frame Attributes

```html
<frame
    src="page.html"           <!-- Source file -->
    name="mainframe"          <!-- Frame name -->
    scrolling="yes"           <!-- yes/no/auto -->
    noresize                  <!-- Prevent resizing -->
    frameborder="0">          <!-- Border (0 or 1) -->
```

---

### 6. Targeting Frames with Links

**Problem:** When you click a link in the menu frame, where should the new page load?

**Solution:** Use the `target` attribute

```html
<!-- menu.html -->
<a href="home.html" target="content">Home</a>
<a href="about.html" target="content">About</a>
<a href="contact.html" target="content">Contact</a>
```

**Target Values:**

- `target="framename"` - Load in named frame
- `target="_self"` - Load in same frame
- `target="_parent"` - Load in parent frameset
- `target="_top"` - Load in full window (breaks out of frames)
- `target="_blank"` - Load in new window

---

### 7. Complete Frame Example (Old Way)

**File: index.html (Main frameset)**

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Website (OLD FRAME METHOD - DON'T USE)</title>
</head>
<frameset rows="100, *">
    <!-- Header frame -->
    <frame src="header.html" name="header" noresize scrolling="no">

    <!-- Content area with menu and main -->
    <frameset cols="200, *">
        <frame src="menu.html" name="menu">
        <frame src="home.html" name="content">
    </frameset>

    <!-- Fallback for browsers that don't support frames -->
    <noframes>
        <body>
            <p>Your browser does not support frames.
            <a href="home.html">Click here</a> to view the site.</p>
        </body>
    </noframes>
</frameset>
</html>
```

**File: header.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Header</title>
    <style>
        body { background-color: #333; color: white; text-align: center; margin: 0; padding: 20px; }
    </style>
</head>
<body>
    <h1>My Website</h1>
</body>
</html>
```

**File: menu.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Menu</title>
    <style>
        body { background-color: #f0f0f0; padding: 10px; }
        a { display: block; padding: 10px; text-decoration: none; color: black; }
        a:hover { background-color: #ddd; }
    </style>
</head>
<body>
    <h3>Navigation</h3>
    <a href="home.html" target="content">Home</a>
    <a href="about.html" target="content">About</a>
    <a href="services.html" target="content">Services</a>
    <a href="contact.html" target="content">Contact</a>
</body>
</html>
```

**File: home.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Home</title>
</head>
<body>
    <h2>Welcome to Our Website</h2>
    <p>This is the home page content.</p>
</body>
</html>
```

---

### 8. Inline Frames: `<iframe>`

**What is an Iframe?**

An iframe (inline frame) embeds another HTML page within the current page. **Unlike framesets, iframes are still supported and widely used.**

**Basic Syntax:**

```html
<iframe src="page.html" width="600" height="400"></iframe>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Iframe Example</title>
</head>
<body>
    <h1>My Website</h1>

    <p>Here's an embedded page:</p>

    <iframe
        src="embedded-content.html"
        width="800"
        height="600"
        frameborder="0"
        title="Embedded Content">
    </iframe>

    <p>Content continues after iframe...</p>
</body>
</html>
```

**Iframe Attributes:**

```html
<iframe
    src="url"                  <!-- Source URL -->
    width="800"                <!-- Width -->
    height="600"               <!-- Height -->
    frameborder="0"            <!-- Border (0 or 1) -->
    scrolling="auto"           <!-- Scrollbars -->
    name="iframename"          <!-- Name for targeting -->
    title="Description">       <!-- Accessibility -->
</iframe>
```

---

### 9. Modern Iframe Uses

#### a) Embedding YouTube Videos

```html
<iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/VIDEO_ID"
    frameborder="0"
    allowfullscreen>
</iframe>
```

#### b) Embedding Google Maps

```html
<iframe
    src="https://www.google.com/maps/embed?..."
    width="600"
    height="450"
    style="border:0;"
    allowfullscreen=""
    loading="lazy">
</iframe>
```

#### c) Embedding External Content

```html
<!DOCTYPE html>
<html>
<head>
    <title>News Portal</title>
</head>
<body>
    <h1>Today's News</h1>

    <h2>Weather Widget</h2>
    <iframe
        src="https://weatherwidget.example.com"
        width="100%"
        height="200"
        style="border: 1px solid #ddd;">
    </iframe>

    <h2>Live Sports Score</h2>
    <iframe
        src="https://scores.example.com"
        width="100%"
        height="400">
    </iframe>
</body>
</html>
```

---

### 10. Why Frames Were Deprecated

**Problems with Framesets:**

❌ **SEO Issues**: Search engines couldn't index framed content properly
❌ **Bookmarking Problems**: Couldn't bookmark specific content states
❌ **Printing Issues**: Difficult to print framed pages
❌ **Accessibility**: Screen readers had trouble navigating
❌ **URL Issues**: URL didn't change when navigating
❌ **Mobile Unfriendly**: Didn't work well on small screens
❌ **Maintenance**: Harder to maintain multiple HTML files

---

### 11. Modern Alternatives to Frames

Instead of frames, use these modern approaches:

#### a) CSS Grid/Flexbox for Layout

```html
<!DOCTYPE html>
<html>
<head>
    <title>Modern Layout</title>
    <style>
        body { margin: 0; font-family: Arial; }
        .container {
            display: grid;
            grid-template-areas:
                "header header"
                "sidebar main"
                "footer footer";
            grid-template-rows: 100px 1fr 80px;
            grid-template-columns: 200px 1fr;
            height: 100vh;
        }
        .header { grid-area: header; background: #333; color: white; padding: 20px; }
        .sidebar { grid-area: sidebar; background: #f0f0f0; padding: 20px; }
        .main { grid-area: main; padding: 20px; }
        .footer { grid-area: footer; background: #333; color: white; padding: 20px; }
    </style>
</head>
<body>
    <div class="container">
        <div class="header"><h1>My Website</h1></div>
        <div class="sidebar">
            <h3>Navigation</h3>
            <a href="#home">Home</a><br>
            <a href="#about">About</a><br>
            <a href="#contact">Contact</a>
        </div>
        <div class="main">
            <h2>Main Content</h2>
            <p>This is the main content area.</p>
        </div>
        <div class="footer">© 2025 My Website</div>
    </div>
</body>
</html>
```

#### b) JavaScript for Dynamic Content

```html
<!DOCTYPE html>
<html>
<head>
    <title>SPA (Single Page Application)</title>
    <style>
        #content { padding: 20px; min-height: 400px; }
    </style>
</head>
<body>
    <nav>
        <button onclick="loadPage('home')">Home</button>
        <button onclick="loadPage('about')">About</button>
        <button onclick="loadPage('contact')">Contact</button>
    </nav>

    <div id="content">
        <h2>Welcome</h2>
        <p>Click a menu item above.</p>
    </div>

    <script>
        function loadPage(page) {
            const content = {
                home: '<h2>Home</h2><p>Welcome to our website!</p>',
                about: '<h2>About</h2><p>We are a web development company.</p>',
                contact: '<h2>Contact</h2><p>Email: info@example.com</p>'
            };
            document.getElementById('content').innerHTML = content[page];
        }
    </script>
</body>
</html>
```

#### c) Server-Side Includes

```html
<!-- Using PHP includes -->
<!DOCTYPE html>
<html>
<head>
    <title>My Site</title>
</head>
<body>
    <?php include 'header.php'; ?>

    <div class="content">
        <h1>Main Content</h1>
    </div>

    <?php include 'footer.php'; ?>
</body>
</html>
```

---

### 12. Iframe Best Practices (Still Valid)

✅ **Always include title attribute** for accessibility
✅ **Set appropriate dimensions**
✅ **Use sandbox attribute** for security:

```html
<iframe
    src="untrusted-content.html"
    sandbox="allow-scripts allow-same-origin"
    title="External Content">
</iframe>
```

✅ **Lazy loading** for performance:

```html
<iframe src="video.html" loading="lazy"></iframe>
```

❌ **Don't use for main navigation** (use regular HTML instead)
❌ **Don't overuse** (impacts performance)

---

### Summary

**Key Takeaways:**

✅ **Framesets are DEPRECATED** - Don't use `<frameset>`, `<frame>`
✅ **Iframes are still valid** - Use `<iframe>` for embedding content
✅ **Modern alternatives**: CSS Grid, Flexbox, JavaScript SPAs
✅ **Iframe uses**: Embed videos, maps, external widgets
✅ **Security**: Use `sandbox` attribute with iframes
✅ **Accessibility**: Always include `title` on iframes

**Why Learn About Frames?**

- Understand legacy code
- Know why they were removed
- Appreciate modern solutions
- Recognize deprecated practices

**Modern Approach:**

```html
<!-- DON'T USE -->
<frameset>
    <frame src="menu.html">
</frameset>

<!-- USE INSTEAD -->
<div class="layout">
    <nav>Menu content here</nav>
    <main>Main content here</main>
</div>
```

**Iframe (Still Valid):**

```html
<!-- Embed external content -->
<iframe
    src="https://www.youtube.com/embed/VIDEO_ID"
    title="Video Title"
    width="560"
    height="315">
</iframe>
```

**Next Steps:**
Now you understand frames and their modern alternatives! Next, you'll learn about HTML forms - one of the most important features for user interaction!
