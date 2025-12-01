# Chapter 2: Introduction to HTML - Part 4
## Images and Anchors

### 1. The Image Element (`<img>`)

**What is an Image Element?**

The `<img>` tag is used to embed images in a web page. It's a **self-closing tag** (no closing tag needed).

**Basic Syntax:**
```html
<img src="image-path.jpg" alt="description">
```

**Required Attributes:**

1. **`src`** (source): Path to the image file
2. **`alt`** (alternative text): Description of the image

---

### 2. Image Source (`src` Attribute)

The `src` attribute specifies where the browser should find the image.

**Three Types of Paths:**

#### a) Relative Path (Same Folder)
```html
<img src="photo.jpg" alt="My Photo">
```
```
📁 mywebsite/
  ├── index.html
  └── photo.jpg ← image in same folder
```

#### b) Relative Path (Subfolder)
```html
<img src="images/photo.jpg" alt="My Photo">
```
```
📁 mywebsite/
  ├── index.html
  └── 📁 images/
      └── photo.jpg ← image in subfolder
```

#### c) Absolute Path (Full URL)
```html
<img src="https://example.com/images/photo.jpg" alt="My Photo">
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Image Example</title>
</head>
<body>
    <h1>My Photo Gallery</h1>

    <!-- Image in same folder -->
    <img src="sunset.jpg" alt="Beautiful Sunset">

    <!-- Image in subfolder -->
    <img src="photos/mountain.jpg" alt="Mountain View">

    <!-- Image from web -->
    <img src="https://picsum.photos/300/200" alt="Random Photo">
</body>
</html>
```

**Real-World Analogy:**

Think of `src` like giving directions:
- **Relative path**: "Go to the next room" (same folder)
- **Relative path with folder**: "Go upstairs to the bedroom" (subfolder)
- **Absolute path**: "123 Main Street, Kathmandu" (complete web address)

---

### 3. Alternative Text (`alt` Attribute)

**Why is `alt` Important?**

1. **Accessibility**: Screen readers speak the alt text for visually impaired users
2. **SEO**: Search engines use alt text to understand images
3. **Fallback**: Shows if image fails to load

**Good vs Bad Alt Text:**

❌ **Bad**:
```html
<img src="image1.jpg" alt="image">
<img src="photo.jpg" alt="">  <!-- Empty alt for important image -->
<img src="pic.jpg" alt="img_20231201_001.jpg">  <!-- Filename -->
```

✅ **Good**:
```html
<img src="student.jpg" alt="Student reading a book in library">
<img src="logo.jpg" alt="Tribhuvan University Logo">
<img src="graph.jpg" alt="Bar chart showing student enrollment from 2020-2025">
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Alt Text Example</title>
</head>
<body>
    <h1>University Campus</h1>

    <!-- Descriptive alt text -->
    <img src="campus.jpg" alt="Tribhuvan University main gate with mountains in background">

    <h2>Faculty Members</h2>

    <!-- Alt describes person -->
    <img src="prof1.jpg" alt="Dr. Ram Sharma, Professor of Computer Science">
    <img src="prof2.jpg" alt="Dr. Sita Koirala, Associate Professor of Mathematics">

    <h2>Research Lab</h2>

    <!-- Alt explains what's in the image -->
    <img src="lab.jpg" alt="Students working on computers in the research laboratory">
</body>
</html>
```

---

### 4. Image Size: `width` and `height`

**Controlling Image Dimensions:**

```html
<!-- Using pixels -->
<img src="photo.jpg" alt="Photo" width="300" height="200">

<!-- Using percentage (relative to container) -->
<img src="photo.jpg" alt="Photo" width="50%">
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Image Sizing</title>
</head>
<body>
    <h1>Different Image Sizes</h1>

    <!-- Small thumbnail -->
    <h2>Small (100x100)</h2>
    <img src="flower.jpg" alt="Rose flower" width="100" height="100">

    <!-- Medium size -->
    <h2>Medium (300x200)</h2>
    <img src="flower.jpg" alt="Rose flower" width="300" height="200">

    <!-- Large size -->
    <h2>Large (600x400)</h2>
    <img src="flower.jpg" alt="Rose flower" width="600" height="400">

    <!-- Responsive (50% of page width) -->
    <h2>Responsive (50%)</h2>
    <img src="flower.jpg" alt="Rose flower" width="50%">
</body>
</html>
```

**Important Notes:**

⚠️ **Aspect Ratio**: Setting both width and height can distort the image

```html
<!-- Original image is 1000x600 (ratio 5:3) -->

<!-- Good: maintains ratio -->
<img src="photo.jpg" alt="Photo" width="500">  <!-- Height auto-calculated -->

<!-- Bad: distorted -->
<img src="photo.jpg" alt="Photo" width="500" height="200">  <!-- Wrong ratio -->
```

**Best Practice:** Set only width or height, let browser calculate the other to maintain aspect ratio, OR use CSS.

---

### 5. Other Image Attributes

**`title` Attribute** (Tooltip on hover):

```html
<img src="flag.jpg" alt="Nepal Flag" title="National Flag of Nepal">
```

**`loading` Attribute** (Lazy loading - HTML5):

```html
<!-- Loads only when near viewport -->
<img src="large-image.jpg" alt="Big Photo" loading="lazy">
```

**Complete Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Image Attributes</title>
</head>
<body>
    <h1>Nepal Tourism</h1>

    <img
        src="photos/everest.jpg"
        alt="Mount Everest peak covered in snow"
        title="Highest mountain in the world - 8,849m"
        width="600"
        loading="lazy">

    <p>
        Mount Everest, known as Sagarmatha in Nepali, is the tallest
        mountain in the world.
    </p>
</body>
</html>
```

---

### 6. Making Images Clickable

Wrap an `<img>` inside an `<a>` tag:

```html
<a href="full-image.jpg">
    <img src="thumbnail.jpg" alt="Click to view full size">
</a>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Clickable Images</title>
</head>
<body>
    <h1>Photo Gallery</h1>
    <p>Click on thumbnails to view full size:</p>

    <!-- Clickable thumbnail -->
    <a href="images/mountain-full.jpg">
        <img src="images/mountain-thumb.jpg" alt="Mountain view" width="200">
    </a>

    <a href="images/lake-full.jpg">
        <img src="images/lake-thumb.jpg" alt="Lake view" width="200">
    </a>
</body>
</html>
```

---

### 7. The Anchor Element (`<a>`)

**What is an Anchor?**

The `<a>` tag (anchor) creates **hyperlinks** - clickable text or images that take users to other pages.

**Basic Syntax:**
```html
<a href="destination-url">Link Text</a>
```

**Example:**

```html
<a href="https://www.google.com">Go to Google</a>
```

**Real-World Analogy:**

Think of an anchor like a doorway:
- The **link text** is the door sign ("Kitchen", "Bedroom")
- The **href** is the actual room it leads to
- Clicking the link is like walking through the door

---

### 8. Types of Links

#### a) External Links (Other Websites)

```html
<a href="https://www.tribhuvan-university.edu.np">Visit TU Website</a>
<a href="https://www.google.com">Search on Google</a>
```

#### b) Internal Links (Same Website)

```html
<!-- Link to another page in same folder -->
<a href="about.html">About Us</a>

<!-- Link to page in subfolder -->
<a href="pages/contact.html">Contact</a>

<!-- Link to parent folder -->
<a href="../index.html">Home</a>
```

#### c) Email Links

```html
<a href="mailto:info@example.com">Send us an email</a>
```

#### d) Phone Links (especially useful on mobile)

```html
<a href="tel:+9779841234567">Call us: 9841234567</a>
```

#### e) Links to Same Page (Jump to Section)

```html
<!-- Link -->
<a href="#contact-section">Go to Contact Section</a>

<!-- Target section -->
<h2 id="contact-section">Contact Us</h2>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Links Example</title>
</head>
<body>
    <h1>My Website</h1>

    <!-- Navigation menu -->
    <nav>
        <a href="#about">About</a> |
        <a href="#services">Services</a> |
        <a href="#contact">Contact</a>
    </nav>

    <hr>

    <!-- About Section -->
    <section id="about">
        <h2>About Us</h2>
        <p>We are a web development company.</p>
    </section>

    <!-- Services Section -->
    <section id="services">
        <h2>Our Services</h2>
        <p>We offer web design and development.</p>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2>Contact Us</h2>
        <p>Email: <a href="mailto:info@example.com">info@example.com</a></p>
        <p>Phone: <a href="tel:+9779841234567">9841234567</a></p>
    </section>

    <!-- External link -->
    <p>
        Visit our partner:
        <a href="https://www.example.com">Example Company</a>
    </p>
</body>
</html>
```

---

### 9. The `target` Attribute

**Opening Links in New Tab/Window:**

```html
<a href="https://www.google.com" target="_blank">Open Google in new tab</a>
```

**`target` Values:**

| Value | Effect |
|-------|--------|
| `_self` | Opens in same tab (default) |
| `_blank` | Opens in new tab/window |
| `_parent` | Opens in parent frame |
| `_top` | Opens in full window |

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Target Attribute</title>
</head>
<body>
    <h1>External Resources</h1>

    <!-- Opens in same tab -->
    <p>
        <a href="about.html">About Page</a> (same tab)
    </p>

    <!-- Opens in new tab -->
    <p>
        <a href="https://www.wikipedia.org" target="_blank">
            Wikipedia
        </a> (new tab)
    </p>

    <p>
        <a href="https://www.youtube.com" target="_blank">
            YouTube
        </a> (new tab)
    </p>
</body>
</html>
```

**Best Practice:** Use `target="_blank"` for external sites, keep internal navigation in same tab.

---

### 10. The `title` Attribute for Links

Shows a tooltip when hovering over the link:

```html
<a href="about.html" title="Learn more about our company">About Us</a>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Link Titles</title>
</head>
<body>
    <h1>Useful Links</h1>

    <p>
        <a href="https://www.google.com"
           target="_blank"
           title="Search engine - opens in new tab">
            Google
        </a>
    </p>

    <p>
        <a href="tutorial.html"
           title="Step-by-step HTML tutorial">
            HTML Tutorial
        </a>
    </p>
</body>
</html>
```

---

### 11. Download Links

Force browser to download file instead of opening it:

```html
<a href="document.pdf" download>Download PDF</a>

<!-- Specify download filename -->
<a href="report-2025.pdf" download="Annual-Report.pdf">Download Annual Report</a>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Download Links</title>
</head>
<body>
    <h1>Resources</h1>

    <h2>Download Course Materials</h2>

    <ul>
        <li>
            <a href="files/syllabus.pdf" download>
                Download Syllabus (PDF)
            </a>
        </li>
        <li>
            <a href="files/lecture-notes.pdf" download="HTML-Notes.pdf">
                Download Lecture Notes
            </a>
        </li>
        <li>
            <a href="files/assignment.docx" download>
                Download Assignment
            </a>
        </li>
    </ul>
</body>
</html>
```

---

### 12. Styling Links with CSS (Preview)

**Default Link Styles:**

```html
<style>
    /* Unvisited link */
    a:link {
        color: blue;
        text-decoration: underline;
    }

    /* Visited link */
    a:visited {
        color: purple;
    }

    /* Mouse hover */
    a:hover {
        color: red;
        text-decoration: none;
    }

    /* Active (being clicked) */
    a:active {
        color: orange;
    }
</style>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Styled Links</title>
    <style>
        /* Remove underline */
        .no-underline {
            text-decoration: none;
        }

        /* Button-style link */
        .button-link {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            display: inline-block;
        }

        .button-link:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>Styled Links</h1>

    <!-- Regular link -->
    <p><a href="page.html">Regular Link</a></p>

    <!-- No underline -->
    <p><a href="page.html" class="no-underline">Link Without Underline</a></p>

    <!-- Button style -->
    <p><a href="page.html" class="button-link">Button Link</a></p>
</body>
</html>
```

---

### 13. Comprehensive Example: Portfolio Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>John Doe - Web Developer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        .profile-pic {
            width: 200px;
            border-radius: 50%;
        }
        .social-link {
            margin-right: 15px;
            text-decoration: none;
        }
        .project-img {
            width: 300px;
            border: 1px solid #ddd;
            margin: 10px;
        }
    </style>
</head>
<body>
    <!-- Header with profile image -->
    <header>
        <img src="images/profile.jpg"
             alt="John Doe - Web Developer"
             class="profile-pic"
             title="John Doe">
        <h1>John Doe</h1>
        <p>Web Developer | Designer | Freelancer</p>
    </header>

    <!-- Navigation -->
    <nav>
        <a href="#about">About</a> |
        <a href="#projects">Projects</a> |
        <a href="#contact">Contact</a>
    </nav>

    <hr>

    <!-- About Section -->
    <section id="about">
        <h2>About Me</h2>
        <p>
            I'm a passionate web developer from Kathmandu, Nepal.
            I specialize in creating beautiful and functional websites.
        </p>

        <!-- Social Media Links -->
        <p>
            <a href="https://github.com/johndoe"
               target="_blank"
               class="social-link"
               title="Visit my GitHub profile">
                GitHub
            </a>
            <a href="https://linkedin.com/in/johndoe"
               target="_blank"
               class="social-link"
               title="Connect on LinkedIn">
                LinkedIn
            </a>
            <a href="https://twitter.com/johndoe"
               target="_blank"
               class="social-link"
               title="Follow me on Twitter">
                Twitter
            </a>
        </p>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2>My Projects</h2>

        <!-- Project 1 -->
        <div>
            <h3>E-Commerce Website</h3>
            <a href="https://example-shop.com" target="_blank">
                <img src="images/project1.jpg"
                     alt="E-commerce website homepage"
                     class="project-img">
            </a>
            <p>A full-featured online shopping platform.</p>
            <a href="https://example-shop.com" target="_blank">View Live Site</a>
        </div>

        <!-- Project 2 -->
        <div>
            <h3>Restaurant Website</h3>
            <a href="https://example-restaurant.com" target="_blank">
                <img src="images/project2.jpg"
                     alt="Restaurant website with menu"
                     class="project-img">
            </a>
            <p>Website for a local restaurant with online ordering.</p>
            <a href="https://example-restaurant.com" target="_blank">View Live Site</a>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2>Contact Me</h2>
        <p>
            <strong>Email:</strong>
            <a href="mailto:john@example.com">john@example.com</a>
        </p>
        <p>
            <strong>Phone:</strong>
            <a href="tel:+9779841234567">+977 9841234567</a>
        </p>
        <p>
            <a href="files/resume.pdf" download="JohnDoe-Resume.pdf">
                Download My Resume (PDF)
            </a>
        </p>
    </section>

    <!-- Footer -->
    <footer>
        <hr>
        <p>
            <small>© 2025 John Doe. All rights reserved.</small>
        </p>
        <p>
            <a href="#" title="Back to top">↑ Back to Top</a>
        </p>
    </footer>
</body>
</html>
```

---

### 14. Best Practices

**For Images:**

✅ Always include `alt` text
✅ Optimize image file size (compress before uploading)
✅ Use appropriate format (JPEG for photos, PNG for graphics/logos)
✅ Use descriptive file names (`sunset-beach.jpg` not `IMG001.jpg`)
✅ Consider responsive images for mobile devices

**For Links:**

✅ Use descriptive link text ("Download Annual Report" not "Click Here")
✅ Open external links in new tab (`target="_blank"`)
✅ Keep internal links in same tab
✅ Use `title` attribute for additional context
✅ Make sure links are clearly visible
✅ Test all links before publishing

---

### Summary

**Key Takeaways:**

✅ **`<img>`**: Embeds images, requires `src` and `alt`
✅ **`src`**: Path to image (relative or absolute)
✅ **`alt`**: Alternative text for accessibility
✅ **`width`/`height`**: Control image dimensions
✅ **`<a>`**: Creates hyperlinks
✅ **`href`**: Link destination
✅ **`target="_blank"`**: Opens in new tab
✅ **Link types**: External, internal, email, phone, same-page
✅ **`download`**: Forces file download
✅ **Clickable images**: Wrap `<img>` in `<a>`

**Quick Reference:**

```html
<!-- Image -->
<img src="photo.jpg" alt="Description" width="300">

<!-- Link -->
<a href="page.html">Link Text</a>

<!-- Link in new tab -->
<a href="https://example.com" target="_blank">External Link</a>

<!-- Clickable image -->
<a href="destination.html">
    <img src="image.jpg" alt="Description">
</a>

<!-- Email link -->
<a href="mailto:email@example.com">Email Us</a>

<!-- Download link -->
<a href="file.pdf" download>Download PDF</a>
```

**Next Steps:**
Now you understand images and links! Next, you'll learn about lists to organize information in ordered, unordered, and definition formats.
