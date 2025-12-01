# Chapter 2: Introduction to HTML - Part 9
## Semantic HTML5 Elements

### 1. Introduction to Semantic HTML

**What is Semantic HTML?**

Semantic HTML uses tags that **clearly describe their meaning** to both the browser and the developer. The tag name tells you what kind of content it contains.

**Non-Semantic vs Semantic:**

```html
<!-- Non-semantic (no meaning) -->
<div id="header">...</div>
<div class="navigation">...</div>
<div id="main-content">...</div>

<!-- Semantic (clear meaning) -->
<header>...</header>
<nav>...</nav>
<main>...</main>
```

**Real-World Analogy:**

Think of semantic HTML like labeled boxes when moving house:
- **Non-semantic**: All boxes look the same, labeled "Box 1", "Box 2"
- **Semantic**: Boxes labeled "Kitchen Items", "Books", "Clothes"

The second approach makes it immediately clear what's inside!

---

### 2. Why Use Semantic HTML?

**Benefits:**

✅ **SEO (Search Engine Optimization)**: Google understands your content better
✅ **Accessibility**: Screen readers can navigate properly
✅ **Readability**: Developers understand code structure
✅ **Maintainability**: Easier to update and modify
✅ **Consistency**: Standard structure across websites

**Impact Example:**

```html
<!-- Search engines don't know what this is -->
<div class="article-section">
    <div class="title">Breaking News</div>
    <div class="content">...</div>
</div>

<!-- Search engines understand this is an article! -->
<article>
    <h1>Breaking News</h1>
    <p>...</p>
</article>
```

---

### 3. The `<header>` Element

**What is `<header>`?**

Represents introductory content or navigation. Usually contains logo, site title, navigation menus.

**Can Be Used:**
- At page level (site header)
- Within `<article>` or `<section>` (content header)

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Semantic Header</title>
    <style>
        header {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <!-- Page header -->
    <header>
        <h1>My Website</h1>
        <p>Welcome to our amazing site</p>
    </header>

    <!-- Article with its own header -->
    <article>
        <header>
            <h2>Article Title</h2>
            <p>By John Doe | Published: Dec 1, 2025</p>
        </header>
        <p>Article content goes here...</p>
    </article>
</body>
</html>
```

---

### 4. The `<nav>` Element

**What is `<nav>`?**

Contains navigation links to other pages or sections within the current page.

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Navigation Example</title>
    <style>
        nav {
            background-color: #4CAF50;
            padding: 10px;
        }
        nav a {
            color: white;
            text-decoration: none;
            padding: 10px 15px;
            display: inline-block;
        }
        nav a:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>My Website</h1>

        <!-- Main navigation -->
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#services">Services</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main>
        <p>Main content here...</p>
    </main>

    <!-- Footer navigation -->
    <footer>
        <nav>
            <a href="#privacy">Privacy Policy</a>
            <a href="#terms">Terms of Service</a>
            <a href="#sitemap">Sitemap</a>
        </nav>
    </footer>
</body>
</html>
```

---

### 5. The `<main>` Element

**What is `<main>`?**

Represents the **dominant content** of the page. Should be unique to the document (don't repeat in header/footer/sidebar).

**Rules:**
- Only **one** `<main>` per page
- Should not be a descendant of `<article>`, `<aside>`, `<footer>`, `<header>`, or `<nav>`

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Main Element</title>
</head>
<body>
    <header>
        <h1>Site Logo</h1>
        <nav>
            <a href="#home">Home</a>
            <a href="#blog">Blog</a>
        </nav>
    </header>

    <!-- Main content (unique to this page) -->
    <main>
        <h1>Welcome to Our Blog</h1>
        <p>This is the main content area of the page.</p>

        <article>
            <h2>Blog Post Title</h2>
            <p>Blog post content...</p>
        </article>
    </main>

    <footer>
        <p>© 2025 My Website</p>
    </footer>
</body>
</html>
```

---

### 6. The `<section>` Element

**What is `<section>`?**

Represents a thematic grouping of content, typically with a heading. Used to divide content into logical sections.

**When to Use:**
- Group related content together
- Usually has a heading (`<h2>`, `<h3>`, etc.)
- Makes sense to list in a table of contents

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Section Example</title>
    <style>
        section {
            margin: 20px 0;
            padding: 20px;
            border: 1px solid #ddd;
        }
    </style>
</head>
<body>
    <main>
        <h1>Programming Courses</h1>

        <!-- Each section is a thematic group -->
        <section>
            <h2>Web Development</h2>
            <p>Learn HTML, CSS, and JavaScript to build websites.</p>
            <ul>
                <li>HTML Fundamentals</li>
                <li>CSS Styling</li>
                <li>JavaScript Basics</li>
            </ul>
        </section>

        <section>
            <h2>Data Science</h2>
            <p>Master Python and data analysis techniques.</p>
            <ul>
                <li>Python Programming</li>
                <li>Data Analysis</li>
                <li>Machine Learning</li>
            </ul>
        </section>

        <section>
            <h2>Mobile Development</h2>
            <p>Create apps for iOS and Android platforms.</p>
            <ul>
                <li>React Native</li>
                <li>Flutter</li>
                <li>Swift & Kotlin</li>
            </ul>
        </section>
    </main>
</body>
</html>
```

---

### 7. The `<article>` Element

**What is `<article>`?**

Represents a **self-contained** piece of content that could be distributed independently (blog post, news article, forum post, product card).

**Test:** Could this be in an RSS feed? If yes, use `<article>`.

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Article Example</title>
    <style>
        article {
            background-color: #f9f9f9;
            padding: 20px;
            margin: 20px 0;
            border-left: 4px solid #4CAF50;
        }
        .article-meta {
            color: #666;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <main>
        <h1>Latest News</h1>

        <!-- Independent article 1 -->
        <article>
            <header>
                <h2>New Technology Breakthrough</h2>
                <p class="article-meta">
                    By Ram Sharma | Published: Dec 1, 2025 | Category: Technology
                </p>
            </header>

            <p>
                Scientists have discovered a new method for renewable energy
                production that could revolutionize the industry...
            </p>

            <footer>
                <p>Comments: 15 | Shares: 42</p>
            </footer>
        </article>

        <!-- Independent article 2 -->
        <article>
            <header>
                <h2>Local Festival Celebration</h2>
                <p class="article-meta">
                    By Sita Rai | Published: Nov 30, 2025 | Category: Culture
                </p>
            </header>

            <p>
                The annual Dashain festival brought together thousands of people
                in Kathmandu for celebrations...
            </p>

            <footer>
                <p>Comments: 8 | Shares: 21</p>
            </footer>
        </article>
    </main>
</body>
</html>
```

---

### 8. The `<aside>` Element

**What is `<aside>`?**

Represents content **tangentially related** to the main content. Often used for sidebars, pull quotes, advertisements, related links.

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Aside Example</title>
    <style>
        body {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        aside {
            background-color: #f0f0f0;
            padding: 20px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <main>
        <article>
            <h1>Understanding HTML5</h1>
            <p>
                HTML5 is the latest version of HTML. It introduced many new
                semantic elements that make web pages more meaningful and
                accessible...
            </p>
            <p>
                Semantic elements like header, nav, main, article, and footer
                help both developers and search engines understand page structure...
            </p>
        </article>
    </main>

    <!-- Sidebar with related content -->
    <aside>
        <h3>Related Articles</h3>
        <ul>
            <li><a href="#">CSS3 Features</a></li>
            <li><a href="#">JavaScript ES6</a></li>
            <li><a href="#">Responsive Design</a></li>
        </ul>

        <h3>Quick Tip</h3>
        <p>
            Always validate your HTML using the W3C Validator to ensure
            your code follows web standards!
        </p>

        <h3>Advertisement</h3>
        <div style="background: #ddd; padding: 20px; text-align: center;">
            [Ad Space]
        </div>
    </aside>
</body>
</html>
```

---

### 9. The `<footer>` Element

**What is `<footer>`?**

Represents footer section for its nearest section or page. Usually contains copyright, contact info, links, social media.

**Can Be Used:**
- At page level (site footer)
- Within `<article>` or `<section>`

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Footer Example</title>
    <style>
        body {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }
        main {
            flex: 1;
        }
        footer {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        footer a {
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <header>
        <h1>My Website</h1>
    </header>

    <main>
        <article>
            <h2>Article Title</h2>
            <p>Article content...</p>

            <!-- Article footer -->
            <footer>
                <p>
                    <small>
                        Published by John Doe on Dec 1, 2025<br>
                        Tags: HTML, Web Development, Tutorial
                    </small>
                </p>
            </footer>
        </article>
    </main>

    <!-- Page footer -->
    <footer>
        <p>&copy; 2025 My Website. All rights reserved.</p>
        <p>
            <a href="#privacy">Privacy Policy</a> |
            <a href="#terms">Terms of Service</a> |
            <a href="#contact">Contact Us</a>
        </p>
        <p>Follow us: Facebook | Twitter | Instagram</p>
    </footer>
</body>
</html>
```

---

### 10. The `<figure>` and `<figcaption>` Elements

**What is `<figure>`?**

Represents self-contained content like images, diagrams, code snippets, that is referenced from the main content but could be moved to an appendix.

**`<figcaption>` provides a caption for the figure.

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Figure Example</title>
    <style>
        figure {
            border: 1px solid #ddd;
            padding: 10px;
            margin: 20px 0;
            text-align: center;
        }
        figcaption {
            font-style: italic;
            color: #666;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <article>
        <h1>Mount Everest: The Highest Peak</h1>

        <p>
            Mount Everest is Earth's highest mountain above sea level,
            located in the Mahalangur Himal sub-range of the Himalayas.
        </p>

        <!-- Figure with image -->
        <figure>
            <img src="everest.jpg" alt="Mount Everest" width="500">
            <figcaption>
                Figure 1: Mount Everest, also known as Sagarmatha in Nepali
            </figcaption>
        </figure>

        <p>
            The mountain stands at 8,848.86 meters (29,031.7 feet) above
            sea level, as confirmed by China and Nepal in 2020.
        </p>

        <!-- Figure with code -->
        <figure>
            <pre><code>
function greet(name) {
    return "Hello, " + name + "!";
}
            </code></pre>
            <figcaption>
                Figure 2: JavaScript greeting function example
            </figcaption>
        </figure>

        <!-- Figure with diagram -->
        <figure>
            <svg width="200" height="100">
                <rect width="200" height="100" fill="#4CAF50"/>
                <text x="100" y="55" text-anchor="middle" fill="white">Diagram</text>
            </svg>
            <figcaption>
                Figure 3: Simple diagram illustration
            </figcaption>
        </figure>
    </article>
</body>
</html>
```

---

### 11. Complete Semantic HTML5 Page Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Complete Semantic HTML5 Example</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: Arial, sans-serif; line-height: 1.6; }

        .container { max-width: 1200px; margin: 0 auto; }

        /* Header */
        header {
            background-color: #333;
            color: white;
            padding: 20px 0;
        }
        header h1 { padding: 0 20px; }

        /* Navigation */
        nav {
            background-color: #4CAF50;
        }
        nav ul {
            list-style: none;
            display: flex;
        }
        nav a {
            color: white;
            text-decoration: none;
            padding: 15px 20px;
            display: block;
        }
        nav a:hover {
            background-color: #45a049;
        }

        /* Main layout */
        .content-wrapper {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 20px;
            padding: 20px;
        }

        /* Main content */
        main {
            background-color: white;
        }

        /* Sections */
        section {
            margin-bottom: 30px;
        }

        /* Articles */
        article {
            background-color: #f9f9f9;
            padding: 20px;
            margin-bottom: 20px;
            border-left: 4px solid #4CAF50;
        }

        /* Aside (sidebar) */
        aside {
            background-color: #f0f0f0;
            padding: 20px;
        }
        aside section {
            margin-bottom: 20px;
        }

        /* Footer */
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 20px;
        }
        footer a {
            color: #4CAF50;
        }

        /* Figure */
        figure {
            margin: 20px 0;
            text-align: center;
        }
        figcaption {
            font-style: italic;
            color: #666;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <!-- Page Header -->
    <header>
        <div class="container">
            <h1>Tech Blog Nepal</h1>
            <p>Latest Technology News and Tutorials</p>
        </div>
    </header>

    <!-- Main Navigation -->
    <nav>
        <div class="container">
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#tutorials">Tutorials</a></li>
                <li><a href="#news">News</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Main Content Area -->
    <div class="container content-wrapper">
        <!-- Main Content -->
        <main>
            <!-- Featured Section -->
            <section id="featured">
                <h2>Featured Article</h2>

                <article>
                    <header>
                        <h3>Complete Guide to HTML5 Semantic Elements</h3>
                        <p>By Ram Sharma | Published: Dec 1, 2025 | Category: Web Development</p>
                    </header>

                    <p>
                        HTML5 introduced many semantic elements that give meaning to web page
                        structure. In this comprehensive guide, we'll explore each element...
                    </p>

                    <figure>
                        <img src="html5-structure.png" alt="HTML5 Page Structure" width="100%">
                        <figcaption>Figure 1: Typical HTML5 semantic page structure</figcaption>
                    </figure>

                    <footer>
                        <p>Comments: 45 | Shares: 120 | <a href="#">Read More →</a></p>
                    </footer>
                </article>
            </section>

            <!-- Latest Articles Section -->
            <section id="latest">
                <h2>Latest Articles</h2>

                <article>
                    <header>
                        <h3>Introduction to CSS Grid Layout</h3>
                        <p>By Sita Rai | Dec 1, 2025</p>
                    </header>
                    <p>
                        CSS Grid Layout is a two-dimensional layout system for the web.
                        It lets you organize content into rows and columns...
                    </p>
                    <footer>
                        <a href="#">Read More →</a>
                    </footer>
                </article>

                <article>
                    <header>
                        <h3>JavaScript ES6 Features Explained</h3>
                        <p>By Hari Thapa | Nov 30, 2025</p>
                    </header>
                    <p>
                        ECMAScript 6 (ES6) brought significant improvements to JavaScript.
                        Learn about arrow functions, promises, and more...
                    </p>
                    <footer>
                        <a href="#">Read More →</a>
                    </footer>
                </article>
            </section>
        </main>

        <!-- Sidebar -->
        <aside>
            <!-- About Section -->
            <section>
                <h3>About This Blog</h3>
                <p>
                    We provide free tutorials on web development, programming,
                    and technology news for learners in Nepal and worldwide.
                </p>
            </section>

            <!-- Popular Posts -->
            <section>
                <h3>Popular Posts</h3>
                <ul style="list-style: none;">
                    <li>→ <a href="#">HTML Basics Tutorial</a></li>
                    <li>→ <a href="#">CSS Flexbox Guide</a></li>
                    <li>→ <a href="#">JavaScript for Beginners</a></li>
                    <li>→ <a href="#">Responsive Web Design</a></li>
                </ul>
            </section>

            <!-- Categories -->
            <section>
                <h3>Categories</h3>
                <ul style="list-style: none;">
                    <li>→ Web Development (25)</li>
                    <li>→ Programming (18)</li>
                    <li>→ Design (12)</li>
                    <li>→ Tutorial (30)</li>
                </ul>
            </section>

            <!-- Newsletter -->
            <section>
                <h3>Newsletter</h3>
                <p>Subscribe for weekly updates:</p>
                <form>
                    <input type="email" placeholder="Your email" style="width: 100%; padding: 8px;">
                    <button type="submit" style="width: 100%; padding: 10px; margin-top: 10px; background: #4CAF50; color: white; border: none; cursor: pointer;">
                        Subscribe
                    </button>
                </form>
            </section>
        </aside>
    </div>

    <!-- Page Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2025 Tech Blog Nepal. All rights reserved.</p>

            <nav>
                <a href="#privacy">Privacy Policy</a> |
                <a href="#terms">Terms of Service</a> |
                <a href="#sitemap">Sitemap</a> |
                <a href="#contact">Contact</a>
            </nav>

            <p>
                Follow us on:
                <a href="#">Facebook</a> |
                <a href="#">Twitter</a> |
                <a href="#">Instagram</a>
            </p>
        </div>
    </footer>
</body>
</html>
```

---

### 12. Semantic Elements vs Div/Span

**When to Use What:**

| Element | When to Use | Example |
|---------|-------------|---------|
| `<header>` | Page/section header | Logo, site title |
| `<nav>` | Navigation links | Menu, breadcrumbs |
| `<main>` | Primary content | Unique page content |
| `<section>` | Thematic grouping | Course sections |
| `<article>` | Independent content | Blog posts, news |
| `<aside>` | Related/sidebar content | Sidebar, ads |
| `<footer>` | Page/section footer | Copyright, links |
| `<figure>` | Self-contained content | Images, diagrams |
| `<div>` | No semantic meaning | Generic container |
| `<span>` | Inline, no meaning | Style specific text |

---

### Summary

**Key Takeaways:**

✅ **Semantic HTML = Meaningful tags** (not just `<div>`)
✅ **`<header>`**: Introductory content
✅ **`<nav>`**: Navigation links
✅ **`<main>`**: Primary content (one per page)
✅ **`<section>`**: Thematic grouping
✅ **`<article>`**: Self-contained content
✅ **`<aside>`**: Sidebar or related content
✅ **`<footer>`**: Footer information
✅ **`<figure>` + `<figcaption>`**: Images/diagrams with captions
✅ **Benefits**: Better SEO, accessibility, readability

**Best Practice:** Use semantic elements whenever possible instead of generic `<div>` and `<span>`!

**Next Steps:**
Now you understand semantic HTML! Next, you'll learn about multimedia elements (meta tags, audio, video, canvas) to make your pages more interactive and rich!
