# Chapter 2: Introduction to HTML - Complete Guide

## 📚 Table of Contents

This chapter provides a comprehensive introduction to HTML (HyperText Markup Language), the foundation of web development. Each topic is covered in detail with examples, analogies, and practical demonstrations accessible to learners from all backgrounds, including those without IT experience.

### Topics Covered

1. **[Introduction to HTML & Document Structure](01-intro-html-structure.md)**
   - What is HTML and why do we need it?
   - Basic structure of an HTML document
   - Understanding HTML elements and attributes
   - Creating your first HTML page

2. **[Headings, Paragraphs, and Divisions](02-headings-paragraphs-divisions.md)**
   - Headings (h1 to h6) and their hierarchy
   - Paragraphs for organizing text
   - Divisions (div) for grouping content
   - Best practices and semantic usage

3. **[Text Formatting and Styling](03-text-formatting.md)**
   - Basic formatting: `<b>`, `<i>`, `<small>`
   - Superscript (`<sup>`) and Subscript (`<sub>`)
   - Spacing elements: `<pre>`, `<br>`
   - Text phrases: `<span>`, `<strong>`, `<tt>`
   - When to use which tag

4. **[Images and Anchors](04-images-anchors.md)**
   - Image element (`<img>`) with attributes
   - Image sources, alt text, and sizing
   - Anchor tags (`<a>`) for links
   - Internal and external linking
   - Link navigation and best practices

5. **[Lists](05-lists.md)**
   - Ordered Lists (`<ol>`) with numbering
   - Unordered Lists (`<ul>`) with bullets
   - Definition Lists (`<dl>`) for term-description pairs
   - Nested lists and practical examples

6. **[Tables](06-tables.md)**
   - Table structure (`<table>`, `<tr>`, `<td>`, `<th>`)
   - Table headers, rows, and cells
   - Table attributes: colspan, rowspan
   - Styling tables for better presentation

7. **[Frames](07-frames.md)**
   - Understanding frames (legacy concept)
   - Framesets and frame tags
   - Why frames are deprecated
   - Modern alternatives to frames

8. **[Forms and Form Elements](08-forms.md)**
   - Form structure (`<form>`)
   - Input types: text, password, email, number, etc.
   - Buttons, checkboxes, radio buttons
   - Select dropdowns and text areas
   - ID and Class attributes for form elements

9. **[Semantic HTML5 Elements](09-semantic-html5.md)**
   - `<main>`, `<section>`, `<article>`
   - `<header>`, `<footer>`, `<aside>`, `<nav>`
   - `<figure>` and `<figcaption>`
   - Benefits of semantic HTML

10. **[Multimedia Elements](10-multimedia.md)**
    - Meta tags for page metadata
    - Audio element (`<audio>`)
    - Video element (`<video>`)
    - Canvas element (`<canvas>`) for graphics

11. **[HTML Events](11-html-events.md)**
    - Window events (onload, onresize, etc.)
    - Form element events (onsubmit, onchange, etc.)
    - Keyboard events (onkeydown, onkeyup, onkeypress)
    - Mouse events (onclick, onmouseover, etc.)

---

## 📖 How to Use This Guide

### For Students:
1. **Read in sequence**: Start from topic 1 and progress linearly
2. **Type the examples**: Don't just read—practice coding each example
3. **Use browser DevTools**: Open HTML files in a browser to see results
4. **Experiment**: Modify examples to see how changes affect output
5. **Review summaries**: Each document ends with key takeaways

### For Instructors:
- Each file is self-contained with complete examples
- Real-world analogies help explain technical concepts
- Comparison tables aid visual learning
- Code examples are tested and ready to demonstrate
- Suitable for lectures, lab sessions, and assignments

---

## 🎯 Learning Objectives

By the end of this chapter, you will be able to:

✅ Understand what HTML is and how it structures web content
✅ Create a basic HTML document with proper structure
✅ Use headings, paragraphs, and divisions to organize content
✅ Apply text formatting and styling tags appropriately
✅ Insert images and create hyperlinks
✅ Build ordered, unordered, and definition lists
✅ Create tables for organizing tabular data
✅ Understand frames and their modern alternatives
✅ Build interactive forms with various input elements
✅ Use semantic HTML5 elements for better structure
✅ Embed multimedia (audio, video) in web pages
✅ Handle user interactions with HTML events

---

## 📁 File Structure

```
chapter-2/
├── README.md (this file)
├── 01-intro-html-structure.md
├── 02-headings-paragraphs-divisions.md
├── 03-text-formatting.md
├── 04-images-anchors.md
├── 05-lists.md
├── 06-tables.md
├── 07-frames.md
├── 08-forms.md
├── 09-semantic-html5.md
├── 10-multimedia.md
└── 11-html-events.md
```

---

## 🔑 Key Concepts Summary

### HTML Basics
- **HTML**: HyperText Markup Language - the language of web pages
- **Elements**: Building blocks (tags) like `<p>`, `<h1>`, `<div>`
- **Attributes**: Additional information about elements (id, class, src, href)

### Document Structure
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    Content goes here
  </body>
</html>
```

### Content Organization
- **Headings**: h1 (most important) to h6 (least important)
- **Paragraphs**: `<p>` for text blocks
- **Divisions**: `<div>` for grouping elements

### Formatting
- **Bold**: `<b>` or `<strong>` (strong is semantic)
- **Italic**: `<i>` or `<em>` (em is semantic)
- **Subscript/Superscript**: `<sub>`, `<sup>` (H₂O, x²)

### Links and Images
- **Images**: `<img src="path" alt="description">`
- **Links**: `<a href="url">Link Text</a>`

### Lists
- **Ordered**: `<ol>` (numbered)
- **Unordered**: `<ul>` (bulleted)
- **Definition**: `<dl>` (term-description pairs)

### Forms
- **Form container**: `<form action="" method="">`
- **Inputs**: text, password, email, checkbox, radio
- **Submission**: buttons to send data

### Semantic HTML5
- **Structure**: header, nav, main, section, article, aside, footer
- **Purpose**: Better meaning and accessibility

### Events
- **User interactions**: click, hover, key press, form submit
- **Syntax**: `<button onclick="alert('Hello')">`

---

## 💡 Tips for Success

1. **Practice coding daily**: Build small HTML pages regularly
2. **Use browser DevTools**: Inspect elements on real websites
3. **Validate your HTML**: Use W3C validator to check code
4. **Learn by doing**: Create projects like a resume page, menu, portfolio
5. **Read documentation**: MDN and W3Schools are excellent resources
6. **Join communities**: Ask questions on forums like Stack Overflow

---

## 🛠️ Tools You'll Need

1. **Text Editor**:
   - Visual Studio Code (recommended)
   - Sublime Text
   - Notepad++ (Windows)
   - Any plain text editor

2. **Web Browser**:
   - Google Chrome (recommended for DevTools)
   - Mozilla Firefox
   - Microsoft Edge
   - Safari

3. **Optional**:
   - Browser extensions for HTML validation
   - Live server extensions for auto-reload

---

## 📚 Additional Resources

- **MDN Web Docs**: https://developer.mozilla.org/en-US/docs/Web/HTML
- **W3Schools**: https://www.w3schools.com/html/
- **HTML Validator**: https://validator.w3.org/
- **Can I Use**: https://caniuse.com/ (check browser support)
- **FreeCodeCamp**: Interactive HTML courses

---

## ✅ Self-Assessment Questions

Test your understanding after completing this chapter:

1. What is the difference between `<b>` and `<strong>` tags?
2. When would you use `<div>` vs `<span>`?
3. What are the required attributes for an `<img>` tag?
4. How do you create a link that opens in a new tab?
5. What's the difference between ordered and unordered lists?
6. How do you merge cells in a table?
7. Why are semantic HTML5 elements important?
8. What's the difference between `<input type="text">` and `<textarea>`?
9. Name three mouse events and their use cases.
10. What is the purpose of the `alt` attribute in images?

---

## 🏆 Practice Projects

Apply your learning with these projects:

### Beginner Level
1. **Personal Introduction Page**: Create a page with your name, photo, and bio
2. **Recipe Page**: Build a recipe with ingredients list and steps
3. **Class Schedule**: Make a weekly timetable using tables

### Intermediate Level
4. **Product Catalog**: Create a page with product images, descriptions, and prices
5. **Contact Form**: Build a form with name, email, message, and submit button
6. **Blog Post**: Use semantic HTML5 to structure an article with header, nav, main, aside, footer

### Advanced Level
7. **Restaurant Menu**: Combine tables, images, and lists
8. **Portfolio Website**: Multi-section page with navigation, projects, contact form
9. **Event Registration**: Complex form with different input types and validation

---

## 📝 Quick Reference

### Common HTML Tags

| Tag | Purpose | Example |
|-----|---------|---------|
| `<h1>` to `<h6>` | Headings | `<h1>Main Title</h1>` |
| `<p>` | Paragraph | `<p>Text here</p>` |
| `<div>` | Container | `<div>Group content</div>` |
| `<span>` | Inline container | `<span>Inline text</span>` |
| `<img>` | Image | `<img src="pic.jpg" alt="Picture">` |
| `<a>` | Link | `<a href="page.html">Link</a>` |
| `<ul>` | Unordered list | `<ul><li>Item</li></ul>` |
| `<ol>` | Ordered list | `<ol><li>Item</li></ol>` |
| `<table>` | Table | `<table><tr><td>Cell</td></tr></table>` |
| `<form>` | Form | `<form action=""><input></form>` |

---

**Author Notes**: This content is designed for bachelor-level education with emphasis on practical understanding. All examples use real-world scenarios and are tested for accuracy. Whether you're from an IT background or not, you'll find the explanations clear and accessible.

**Last Updated**: December 2025
