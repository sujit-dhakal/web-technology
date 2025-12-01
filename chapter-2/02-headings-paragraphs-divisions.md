# Chapter 2: Introduction to HTML - Part 2
## Headings, Paragraphs, and Divisions

### 1. HTML Headings (H1 to H6)

**What are Headings?**

Headings are titles or subtitles that organize content into sections. HTML provides six levels of headings, from `<h1>` (most important) to `<h6>` (least important).

**Syntax:**
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Sub-subheading</h3>
<h4>Smaller heading</h4>
<h5>Even smaller heading</h5>
<h6>Smallest heading</h6>
```

**Visual Representation (browser default sizes):**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Heading Examples</title>
</head>
<body>
    <h1>Level 1 Heading - Largest</h1>
    <h2>Level 2 Heading</h2>
    <h3>Level 3 Heading</h3>
    <h4>Level 4 Heading</h4>
    <h5>Level 5 Heading</h5>
    <h6>Level 6 Heading - Smallest</h6>
</body>
</html>
```

**Real-World Analogy:**

Think of headings like the structure of a book:

```
<h1> Book Title
  <h2> Part 1
    <h3> Chapter 1
      <h4> Section 1.1
        <h5> Subsection 1.1.1
          <h6> Minor point
```

---

### 2. Heading Hierarchy and Best Practices

**Proper Hierarchy:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Article Example</title>
</head>
<body>
    <h1>Web Development Guide</h1>

    <h2>Introduction to HTML</h2>
    <p>HTML is the foundation of web pages...</p>

    <h3>What is HTML?</h3>
    <p>HTML stands for HyperText Markup Language...</p>

    <h3>Why Learn HTML?</h3>
    <p>HTML is essential because...</p>

    <h2>CSS Styling</h2>
    <p>CSS makes web pages beautiful...</p>

    <h3>Colors and Fonts</h3>
    <p>You can change colors using...</p>
</body>
</html>
```

**Best Practices:**

| Practice | Why? | Example |
|----------|------|---------|
| **One `<h1>` per page** | Represents the main topic | `<h1>My Portfolio</h1>` |
| **Don't skip levels** | Maintain logical structure | ✅ h1→h2→h3  ❌ h1→h3 |
| **Use for structure, not size** | Use CSS for styling | Don't use h4 just to make text smaller |
| **Be descriptive** | Helps SEO and accessibility | ✅ `<h2>Contact Info</h2>` ❌ `<h2>Info</h2>` |

**Common Mistakes:**

❌ **Wrong**:
```html
<h1>Welcome</h1>
<h3>About</h3>  <!-- Skipped h2 -->
<h5>Contact</h5>  <!-- Skipped h4 -->
```

✅ **Correct**:
```html
<h1>Welcome</h1>
<h2>About</h2>
<h3>My Skills</h3>
<h2>Contact</h2>
```

---

### 3. Paragraphs (`<p>`)

**What are Paragraphs?**

The `<p>` tag defines a paragraph of text. Browsers automatically add space before and after each paragraph.

**Syntax:**
```html
<p>This is a paragraph.</p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Paragraph Example</title>
</head>
<body>
    <h1>About Nepal</h1>

    <p>
        Nepal is a landlocked country in South Asia. It is located mainly in the
        Himalayas, but also includes parts of the Indo-Gangetic Plain.
    </p>

    <p>
        Nepal has a diverse geography, including fertile plains, subalpine forested
        hills, and eight of the world's ten tallest mountains, including Mount Everest.
    </p>

    <p>
        The capital and largest city is Kathmandu. The official language is Nepali,
        and the currency is the Nepalese Rupee.
    </p>
</body>
</html>
```

**Important Notes:**

1. **Whitespace Collapsing**: HTML collapses multiple spaces into one

```html
<!-- Multiple spaces and line breaks in code -->
<p>This    has    many
   spaces    and
   line    breaks.</p>

<!-- Browser displays as: -->
This has many spaces and line breaks.
```

2. **Line Breaks**: New lines in your code don't create new lines on the page

```html
<!-- In your code: -->
<p>
Line 1
Line 2
Line 3
</p>

<!-- Browser shows: -->
Line 1 Line 2 Line 3
```

To create actual line breaks, use `<br>` (covered later).

---

### 4. Divisions (`<div>`)

**What is a Division?**

The `<div>` tag is a **container** that groups other HTML elements together. Think of it as a box that holds related content.

**Syntax:**
```html
<div>
    Content and elements go here
</div>
```

**Key Characteristics:**

- **Block-level element**: Takes full width, starts on new line
- **No visual styling** by default
- **Used for grouping**: Organize related elements
- **Works with CSS**: Apply styles to groups of elements

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Division Example</title>
</head>
<body>
    <div>
        <h2>Student Information</h2>
        <p>Name: Sita Rai</p>
        <p>Roll No: 45</p>
        <p>Class: Bachelor 1st Year</p>
    </div>

    <div>
        <h2>Contact Details</h2>
        <p>Email: sita@example.com</p>
        <p>Phone: 9841234567</p>
    </div>
</body>
</html>
```

**Real-World Analogy:**

Think of a `<div>` like rooms in a house:
- Each `<div>` is a room (kitchen, bedroom, bathroom)
- Each room groups related items (kitchen has stove, fridge, sink)
- You can style each room differently
- Rooms help organize your house (divs organize your webpage)

---

### 5. Practical Comparison: Headings, Paragraphs, Divisions

**Complete Example:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Personal Blog</title>
</head>
<body>
    <!-- Page Header -->
    <div>
        <h1>My Personal Blog</h1>
        <p>Thoughts, stories, and ideas...</p>
    </div>

    <!-- Blog Post 1 -->
    <div>
        <h2>My First Day at University</h2>
        <p>
            Today was my first day at Tribhuvan University. I was both excited
            and nervous. The campus is huge and beautiful.
        </p>
        <p>
            I met many new friends in my class. Everyone was friendly and helpful.
            I'm looking forward to this new chapter in my life.
        </p>
    </div>

    <!-- Blog Post 2 -->
    <div>
        <h2>Learning Web Development</h2>
        <p>
            I've started learning HTML and it's fascinating! I never knew creating
            websites could be this interesting.
        </p>

        <h3>What I've Learned So Far</h3>
        <p>
            I now understand headings, paragraphs, and how to structure content
            using divisions. Next, I'll learn about styling with CSS.
        </p>
    </div>

    <!-- Footer -->
    <div>
        <p>Copyright 2025 - My Blog</p>
    </div>
</body>
</html>
```

**Breakdown:**

```
<div>                    ← Container for header
  <h1>                   ← Main page title (level 1)
  <p>                    ← Tagline/description

<div>                    ← Container for blog post 1
  <h2>                   ← Post title (level 2)
  <p>                    ← First paragraph
  <p>                    ← Second paragraph

<div>                    ← Container for blog post 2
  <h2>                   ← Post title (level 2)
  <p>                    ← Paragraph
  <h3>                   ← Subsection (level 3)
  <p>                    ← Paragraph

<div>                    ← Container for footer
  <p>                    ← Copyright text
```

---

### 6. Using ID and Class with Divisions

**ID Attribute:**

- **Unique** identifier for a single element
- Used once per page
- Syntax: `id="name"`

**Class Attribute:**

- **Reusable** identifier for multiple elements
- Can be used many times
- Syntax: `class="name"`

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>ID and Class Example</title>
    <style>
        /* CSS styling (preview of what you'll learn) */
        #header {
            background-color: lightblue;
            padding: 20px;
        }

        .post {
            border: 1px solid gray;
            margin: 10px;
            padding: 15px;
        }

        .important {
            color: red;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <!-- Unique header section -->
    <div id="header">
        <h1>My Website</h1>
    </div>

    <!-- Multiple posts with same class -->
    <div class="post">
        <h2>Post 1</h2>
        <p>This is the first post.</p>
    </div>

    <div class="post">
        <h2>Post 2</h2>
        <p class="important">This is an important announcement!</p>
    </div>

    <div class="post">
        <h2>Post 3</h2>
        <p>This is the third post.</p>
    </div>
</body>
</html>
```

**Comparison Table:**

| Feature | ID | Class |
|---------|-----|-------|
| **Uniqueness** | Must be unique on page | Can be reused |
| **Syntax** | `id="header"` | `class="post"` |
| **CSS Selector** | `#header { }` | `.post { }` |
| **JavaScript Selection** | `document.getElementById()` | `document.getElementsByClassName()` |
| **Usage** | Unique sections (header, footer) | Repeated patterns (posts, cards) |
| **Multiple Values** | No | Yes: `class="post important"` |

---

### 7. Semantic Structure Example

**Good Structure with Proper Hierarchy:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Restaurant Menu</title>
</head>
<body>
    <!-- Main heading for the page -->
    <h1>Himalayan Restaurant</h1>
    <p>Authentic Nepali Cuisine</p>

    <!-- Menu sections -->
    <div id="appetizers">
        <h2>Appetizers</h2>

        <div class="menu-item">
            <h3>Samosa</h3>
            <p>Crispy pastry filled with spiced potatoes and peas.</p>
            <p>Price: Rs. 50</p>
        </div>

        <div class="menu-item">
            <h3>Momo</h3>
            <p>Steamed dumplings with chicken or vegetables.</p>
            <p>Price: Rs. 120</p>
        </div>
    </div>

    <div id="main-courses">
        <h2>Main Courses</h2>

        <div class="menu-item">
            <h3>Dal Bhat</h3>
            <p>Traditional Nepali meal with lentils, rice, and curry.</p>
            <p>Price: Rs. 200</p>
        </div>

        <div class="menu-item">
            <h3>Chicken Thukpa</h3>
            <p>Hearty noodle soup with vegetables and chicken.</p>
            <p>Price: Rs. 180</p>
        </div>
    </div>

    <div id="footer">
        <h2>Contact Us</h2>
        <p>Phone: 01-4567890</p>
        <p>Location: Thamel, Kathmandu</p>
    </div>
</body>
</html>
```

**Structure Visualization:**

```
h1: Restaurant Name (main title)
  p: Tagline

  div#appetizers (section container)
    h2: Section title
      div.menu-item (item container)
        h3: Item name
        p: Description
        p: Price
      div.menu-item (item container)
        h3: Item name
        p: Description
        p: Price

  div#main-courses (section container)
    h2: Section title
      div.menu-item (item container)
        h3: Item name
        p: Description
        p: Price
```

---

### 8. Common Mistakes and How to Fix Them

**Mistake 1: Using too many `<div>` tags**

❌ **Bad** (div soup):
```html
<div>
    <div>
        <div>
            <p>Some text</p>
        </div>
    </div>
</div>
```

✅ **Good**:
```html
<p>Some text</p>
```

**Mistake 2: Not closing tags**

❌ **Bad**:
```html
<div>
    <h2>Title
    <p>Paragraph
</div>
```

✅ **Good**:
```html
<div>
    <h2>Title</h2>
    <p>Paragraph</p>
</div>
```

**Mistake 3: Using headings for size instead of structure**

❌ **Bad**:
```html
<h1>Main Title</h1>
<h5>I used h5 because I want small text</h5>
```

✅ **Good**:
```html
<h1>Main Title</h1>
<p style="font-size: 14px;">This is small text styled properly</p>
```

**Mistake 4: Multiple `<h1>` tags**

❌ **Bad**:
```html
<h1>Welcome</h1>
<h1>About</h1>
<h1>Contact</h1>
```

✅ **Good**:
```html
<h1>My Website</h1>
<h2>About</h2>
<h2>Contact</h2>
```

---

### 9. Accessibility Considerations

**Why Heading Structure Matters:**

Screen readers (used by visually impaired users) navigate pages using heading structure. Proper headings help them understand content organization.

**Good for Accessibility:**

```html
<h1>University Department</h1>
  <h2>Computer Science</h2>
    <h3>Programs Offered</h3>
    <h3>Faculty Members</h3>
  <h2>Mathematics</h2>
    <h3>Programs Offered</h3>
    <h3>Faculty Members</h3>
```

**Screen reader navigation:**
- "Heading level 1: University Department"
- "Heading level 2: Computer Science"
- "Heading level 3: Programs Offered"

---

### Summary

**Key Takeaways:**

✅ **Headings (`<h1>` to `<h6>`)**: Structure content hierarchically
✅ **One `<h1>` per page**: Represents main topic
✅ **Don't skip heading levels**: Maintain logical progression
✅ **Paragraphs (`<p>`)**: Contain blocks of text
✅ **HTML collapses whitespace**: Multiple spaces become one
✅ **Divisions (`<div>`)**: Container elements for grouping
✅ **ID attribute**: Unique identifier (used once)
✅ **Class attribute**: Reusable identifier (used multiple times)
✅ **Semantic structure**: Helps SEO and accessibility
✅ **Proper nesting**: Close tags in correct order

**Quick Reference:**

```html
<!-- Headings -->
<h1>Most important</h1>
<h2>Second level</h2>
<h3>Third level</h3>

<!-- Paragraphs -->
<p>Text content here</p>

<!-- Divisions -->
<div id="unique-name">
    <div class="reusable-name">
        <h2>Title</h2>
        <p>Content</p>
    </div>
</div>
```

**Next Steps:**
Now that you understand how to structure content with headings, paragraphs, and divisions, you're ready to learn about text formatting to make your content more expressive!
