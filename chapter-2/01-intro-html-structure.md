# Chapter 2: Introduction to HTML - Part 1
## Introduction to HTML & Document Structure

### 1. What is HTML?

**HTML** stands for **HyperText Markup Language**. It's the standard language used to create web pages. Let's break down what each word means:

- **HyperText**: Text that contains links to other texts (you can click and jump to other pages)
- **Markup**: A system of tags/annotations that give structure and meaning to content
- **Language**: A standardized way of writing instructions

**Real-World Analogy:**

Think of HTML like the blueprint of a house:
- The blueprint shows where walls, doors, and windows go
- HTML shows where headings, paragraphs, images, and links go
- The blueprint doesn't show colors or decorations (that's CSS's job)
- HTML doesn't show the structure, not the styling

**Why Do We Need HTML?**

Web browsers (like Chrome, Firefox, Safari) need instructions to display content. HTML provides these instructions. Without HTML:
- Browsers wouldn't know what's a heading vs regular text
- Images wouldn't appear
- Links wouldn't work
- Content would just be plain text with no structure

---

### 2. HTML Elements

**What is an HTML Element?**

An HTML element is a building block of a web page. It usually consists of:
1. **Opening tag**: `<tagname>`
2. **Content**: The text or other elements inside
3. **Closing tag**: `</tagname>`

**Structure:**
```html
<tagname>Content goes here</tagname>
```

**Example:**
```html
<p>This is a paragraph.</p>
```

- `<p>` = Opening tag (starts a paragraph)
- `This is a paragraph.` = Content
- `</p>` = Closing tag (ends the paragraph)

**Self-Closing Elements:**

Some elements don't have content and don't need a closing tag:

```html
<img src="photo.jpg" alt="My Photo">
<br>
<hr>
```

**Real-World Analogy:**

Think of HTML tags like containers:
- `<p>` is like a box labeled "Paragraph"
- You put text inside the box
- `</p>` seals the box
- The browser reads the label and knows "this is a paragraph"

---

### 3. HTML Attributes

**What are Attributes?**

Attributes provide additional information about HTML elements. They are always placed in the opening tag and come in name-value pairs.

**Syntax:**
```html
<tagname attribute="value">Content</tagname>
```

**Common Attributes:**

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `id` | Unique identifier for an element | `<div id="header">` |
| `class` | Categorizes elements (can be reused) | `<p class="intro">` |
| `src` | Source file for images/videos | `<img src="photo.jpg">` |
| `href` | URL for links | `<a href="page.html">` |
| `alt` | Alternative text for images | `<img alt="Description">` |
| `title` | Tooltip text on hover | `<p title="More info">` |
| `style` | Inline CSS styling | `<p style="color:red;">` |

**Example with Multiple Attributes:**
```html
<img src="sunset.jpg" alt="Beautiful Sunset" width="500" height="300" title="Sunset at Beach">
```

**Real-World Analogy:**

If an HTML element is a person:
- The tag name (`<img>`) is their role (photographer)
- Attributes are their characteristics:
  - `id="john"` → Name (unique)
  - `class="professional"` → Category (shared with others)
  - `src="camera.jpg"` → Equipment they use

---

### 4. Basic HTML Document Structure

Every HTML document follows a standard structure. This is like the skeleton of a human body—it's always the same basic framework.

**Complete HTML Document:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is my first paragraph.</p>
</body>
</html>
```

**Let's Break It Down:**

#### 1. `<!DOCTYPE html>`
- **Purpose**: Tells the browser this is an HTML5 document
- **Must be**: The very first line
- **Not a tag**: It's a declaration

#### 2. `<html lang="en">`
- **Purpose**: Root element that wraps all content
- **lang="en"**: Specifies the language (English)
- **Think of it as**: The main container for everything

#### 3. `<head>` Section
The "head" contains **metadata** (information about the page, not visible content)

**Common elements in `<head>`:**

```html
<head>
    <!-- Character encoding for proper text display -->
    <meta charset="UTF-8">

    <!-- Makes site responsive on mobile devices -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- Page title shown in browser tab -->
    <title>My Website</title>

    <!-- Page description for search engines -->
    <meta name="description" content="This is my website about HTML">

    <!-- Link to external CSS file -->
    <link rel="stylesheet" href="styles.css">
</head>
```

#### 4. `<body>` Section
The "body" contains **all visible content** (what users see)

```html
<body>
    <h1>This appears on the page</h1>
    <p>So does this text.</p>
    <img src="photo.jpg" alt="Photo">
</body>
```

**Analogy for Document Structure:**

Think of an HTML document like a letter:

```
<!DOCTYPE html>          →  Envelope type (standard letter)
<html>                   →  The envelope itself
  <head>                 →  Information on the envelope (address, postage)
    <title>             →  Subject line
  </head>
  <body>                 →  The actual letter content inside
    Content here
  </body>
</html>                  →  Seal the envelope
```

---

### 5. Creating Your First HTML Page

**Step-by-Step Guide:**

1. **Open a text editor** (Notepad, VS Code, Sublime Text)

2. **Type this code:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>About Me</title>
</head>
<body>
    <h1>Hello, I'm [Your Name]</h1>
    <p>I'm learning HTML. This is my first web page!</p>
    <p>I'm excited to learn web development.</p>
</body>
</html>
```

3. **Save the file:**
   - File name: `index.html` or `mypage.html`
   - File type: All Files (not .txt)
   - Location: Desktop or any folder you prefer

4. **Open in browser:**
   - Double-click the file, OR
   - Right-click → Open with → Chrome/Firefox

5. **You should see:**
   - A large heading with your name
   - Two paragraphs below it

**Congratulations! You've created your first web page!** 🎉

---

### 6. Understanding Nesting

**What is Nesting?**

Nesting means placing HTML elements inside other HTML elements.

**Correct Nesting:**
```html
<body>
    <div>
        <h1>Title</h1>
        <p>Paragraph inside div</p>
    </div>
</body>
```

The structure:
- `<body>` contains `<div>`
- `<div>` contains `<h1>` and `<p>`

**Rule**: Elements must be closed in the reverse order they were opened.

**WRONG** (tags overlap incorrectly):
```html
<p>This is <strong>bold and <em>italic</strong></em> text</p>
```

**CORRECT**:
```html
<p>This is <strong>bold and <em>italic</em></strong> text</p>
```

**Analogy:**

Think of nesting like Russian dolls (Matryoshka):
- The biggest doll (html) contains everything
- Inside is a medium doll (body)
- Inside that is a small doll (div)
- Inside that is an even smaller doll (p)
- You can't close them in the wrong order!

---

### 7. HTML Comments

**What are Comments?**

Comments are notes in your code that browsers ignore. They're for humans reading the code.

**Syntax:**
```html
<!-- This is a comment -->
```

**Example:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
</head>
<body>
    <!-- Navigation section -->
    <h1>Welcome</h1>

    <!-- Main content area -->
    <p>This is visible to users.</p>

    <!-- TODO: Add more content here later -->
</body>
</html>
```

**Why Use Comments?**

1. **Explain code**: Help others (or future you) understand
2. **Organize sections**: Mark different parts of your page
3. **Temporarily disable code**: Test without deleting

```html
<!--
<p>This paragraph is commented out</p>
<p>It won't appear on the page</p>
-->
```

---

### 8. HTML Element Types

**Block-Level Elements:**

Take up the full width available and start on a new line.

```html
<div>This is a block element</div>
<p>This starts on a new line</p>
<h1>This also starts on a new line</h1>
```

Visual representation:
```
┌────────────────────────────┐
│ <div>Block element</div>   │
└────────────────────────────┘
┌────────────────────────────┐
│ <p>Another block</p>       │
└────────────────────────────┘
```

**Common block elements**: `<div>`, `<p>`, `<h1>-<h6>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<form>`, `<header>`, `<footer>`, `<section>`

**Inline Elements:**

Take only as much width as needed and don't start on a new line.

```html
<p>I can have <span>inline elements</span> and <strong>more inline</strong> in the same line.</p>
```

Visual representation:
```
I can have inline elements and more inline in the same line.
```

**Common inline elements**: `<span>`, `<a>`, `<strong>`, `<em>`, `<b>`, `<i>`, `<img>`, `<br>`, `<input>`, `<label>`

---

### 9. Practical Example: Complete Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Student profile page">
    <title>Student Profile - Ram Sharma</title>
</head>
<body>
    <!-- Page Header -->
    <h1>Student Profile</h1>

    <!-- Personal Information -->
    <h2>Personal Details</h2>
    <p><strong>Name:</strong> Ram Sharma</p>
    <p><strong>Roll Number:</strong> 2024001</p>
    <p><strong>Department:</strong> Computer Science</p>

    <!-- About Section -->
    <h2>About Me</h2>
    <p>
        I am a first-year student at <em>Tribhuvan University</em>.
        I am interested in web development and data science.
    </p>

    <!-- Footer -->
    <p><small>Last updated: December 2025</small></p>
</body>
</html>
```

**What this page includes:**
- Proper document structure with DOCTYPE, html, head, and body
- Meta tags for character encoding and viewport
- Multiple heading levels (h1, h2)
- Paragraphs with formatted text (strong, em)
- Comments to organize code sections
- Semantic use of small tag for footer text

---

### Summary

**Key Takeaways:**

✅ **HTML** = HyperText Markup Language (structure of web pages)
✅ **Elements** = Building blocks with opening and closing tags
✅ **Attributes** = Additional information (name="value")
✅ **Document Structure** = DOCTYPE, html, head, body
✅ **Head** = Metadata (not visible on page)
✅ **Body** = All visible content
✅ **Nesting** = Elements inside elements (like Russian dolls)
✅ **Comments** = Notes for developers `<!-- comment -->`
✅ **Block elements** = Full width, new line
✅ **Inline elements** = Minimal width, same line

**Remember:**
- HTML provides structure, not styling (that's CSS)
- Every tag should close properly
- Attribute values should be in quotes
- Indent nested elements for readability
- Use meaningful names for id and class attributes

**Next Steps:**
Now that you understand HTML basics and document structure, you're ready to learn about specific elements like headings, paragraphs, and divisions in the next section!
