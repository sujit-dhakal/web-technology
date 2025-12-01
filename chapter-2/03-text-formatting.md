# Chapter 2: Introduction to HTML - Part 3
## Text Formatting and Styling

### 1. Introduction to Text Formatting

HTML provides various tags to format text and give it meaning. While CSS is primarily used for styling in modern web development, HTML formatting tags are still important because they add **semantic meaning** to content.

**Why Format Text?**

- Emphasize important information
- Make content more readable
- Add scientific or mathematical notation
- Provide visual hierarchy
- Improve accessibility (screen readers understand semantic tags)

---

### 2. Bold Text: `<b>` vs `<strong>`

**The `<b>` Tag** (Bold)

Makes text bold **without** adding extra importance or emphasis.

```html
<p>This is <b>bold text</b> in a paragraph.</p>
```

**The `<strong>` Tag** (Strong Importance)

Makes text bold **and** indicates it's important.

```html
<p>This is <strong>very important</strong> information.</p>
```

**When to Use Which?**

| Use Case | Tag | Example |
|----------|-----|---------|
| Product name in description | `<b>` | `The <b>iPhone 15</b> is available` |
| Important warning | `<strong>` | `<strong>Warning:</strong> High voltage` |
| Keywords (no emphasis) | `<b>` | `<b>HTML</b> is a markup language` |
| Critical information | `<strong>` | `<strong>Due date:</strong> Tomorrow` |

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Bold Example</title>
</head>
<body>
    <h1>Product Description</h1>

    <!-- Using <b> for visual emphasis only -->
    <p>The <b>ThinkPad X1</b> laptop features a 14-inch display.</p>

    <!-- Using <strong> for important information -->
    <p><strong>Important Notice:</strong> Limited stock available!</p>

    <!-- Combination -->
    <p>
        <strong>Safety Instructions:</strong> Always wear protective gear.
        The tool operates at <b>high speeds</b>.
    </p>
</body>
</html>
```

---

### 3. Italic Text: `<i>` vs `<em>`

**The `<i>` Tag** (Italic)

Makes text italic for **technical terms, foreign words, or thoughts**.

```html
<p>The scientific name is <i>Homo sapiens</i>.</p>
```

**The `<em>` Tag** (Emphasis)

Makes text italic **and** adds emphasis (stress on the word).

```html
<p>You should <em>never</em> share your password.</p>
```

**When to Use Which?**

| Use Case | Tag | Example |
|----------|-----|---------|
| Scientific names | `<i>` | `<i>Panthera tigris</i> (tiger)` |
| Foreign words | `<i>` | `It means <i>thank you</i> in Spanish` |
| Book/movie titles | `<i>` | `I read <i>The Alchemist</i>` |
| Emphasis/stress | `<em>` | `This is <em>really</em> important` |
| Thoughts | `<i>` | `<i>What should I do?</i> she thought` |

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Italic Example</title>
</head>
<body>
    <h1>Language Notes</h1>

    <!-- Using <i> for foreign words -->
    <p>We say <i>namaste</i> as a greeting in Nepal.</p>

    <!-- Using <em> for emphasis -->
    <p>You <em>must</em> complete the assignment by Friday.</p>

    <!-- Using <i> for scientific names -->
    <p>
        The national flower of Nepal is <i>Rhododendron arboreum</i>,
        and it's <em>truly</em> beautiful.
    </p>

    <!-- Using <i> for book titles -->
    <p>My favorite book is <i>Seto Dharti</i> by Amar Neupane.</p>
</body>
</html>
```

---

### 4. Small Text: `<small>`

**The `<small>` Tag**

Displays text in a smaller font size. Used for fine print, disclaimers, copyright notices, legal text.

**Syntax:**
```html
<p>This is normal text. <small>This is smaller text.</small></p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Small Text Example</title>
</head>
<body>
    <h1>Special Offer!</h1>

    <p>Get 50% off on all products!</p>
    <p><small>*Terms and conditions apply. Offer valid until December 31, 2025.</small></p>

    <h2>Product Price</h2>
    <p>Rs. 1,999 <small>(excluding tax)</small></p>

    <!-- Footer with copyright -->
    <footer>
        <p><small>© 2025 My Company. All rights reserved.</small></p>
    </footer>
</body>
</html>
```

**Common Uses:**

- Copyright notices
- Disclaimers
- Fine print
- Side comments
- Date/time stamps in less prominent text

---

### 5. Superscript: `<sup>`

**The `<sup>` Tag**

Displays text as **superscript** (raised above the normal line). Used for exponents, ordinal numbers, footnotes.

**Syntax:**
```html
<p>2<sup>10</sup> = 1024</p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Superscript Example</title>
</head>
<body>
    <h1>Mathematics and Science</h1>

    <!-- Exponents -->
    <p>The formula is: E = mc<sup>2</sup></p>
    <p>Calculate: 5<sup>3</sup> = 125</p>

    <!-- Area calculation -->
    <p>Area of square = side<sup>2</sup></p>
    <p>If side = 5cm, then area = 25cm<sup>2</sup></p>

    <!-- Ordinal numbers -->
    <p>Today is December 1<sup>st</sup>, 2025</p>
    <p>He came 2<sup>nd</sup> in the race</p>
    <p>She ranked 3<sup>rd</sup> in the class</p>

    <!-- Footnotes -->
    <p>
        HTML is a markup language<sup>1</sup> used for creating web pages<sup>2</sup>.
    </p>
    <hr>
    <p><small><sup>1</sup> Markup language = system for annotating text</small></p>
    <p><small><sup>2</sup> Web pages = documents on the World Wide Web</small></p>
</body>
</html>
```

---

### 6. Subscript: `<sub>`

**The `<sub>` Tag**

Displays text as **subscript** (lowered below the normal line). Used for chemical formulas, mathematical notations.

**Syntax:**
```html
<p>H<sub>2</sub>O is water</p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Subscript Example</title>
</head>
<body>
    <h1>Chemistry Formulas</h1>

    <!-- Water -->
    <p>Water: H<sub>2</sub>O</p>

    <!-- Carbon dioxide -->
    <p>Carbon Dioxide: CO<sub>2</sub></p>

    <!-- Glucose -->
    <p>Glucose: C<sub>6</sub>H<sub>12</sub>O<sub>6</sub></p>

    <!-- Sulfuric acid -->
    <p>Sulfuric Acid: H<sub>2</sub>SO<sub>4</sub></p>

    <h2>Mathematical Notation</h2>

    <!-- Variables with subscripts -->
    <p>Variable: x<sub>1</sub>, x<sub>2</sub>, x<sub>3</sub></p>

    <!-- Logarithm -->
    <p>Logarithm: log<sub>10</sub>(100) = 2</p>
</body>
</html>
```

**Combining Superscript and Subscript:**

```html
<!-- Chemical isotope notation -->
<p>Uranium isotope: <sup>235</sup>U<sub>92</sub></p>

<!-- Complex math -->
<p>Sum: x<sub>1</sub><sup>2</sup> + x<sub>2</sub><sup>2</sup></p>
```

---

### 7. Spacing: The `<pre>` Tag

**The `<pre>` Tag** (Preformatted Text)

Preserves **both spaces and line breaks** exactly as you type them. Text is displayed in a monospace font (like Courier).

**Syntax:**
```html
<pre>
    Text with    multiple spaces
    and line breaks
        preserved.
</pre>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Preformatted Text Example</title>
</head>
<body>
    <h1>Code Example</h1>

    <!-- Without <pre> - spaces collapse -->
    <p>
        function hello() {
            console.log("Hello");
        }
    </p>

    <h2>Same code with &lt;pre&gt;</h2>

    <!-- With <pre> - formatting preserved -->
    <pre>
        function hello() {
            console.log("Hello");
        }
    </pre>

    <h2>ASCII Art</h2>
    <pre>
        *****
        *   *
        *   *
        *****
    </pre>

    <h2>Formatted Data</h2>
    <pre>
Name        Age    City
Ram         25     Kathmandu
Sita        23     Pokhara
Hari        27     Lalitpur
    </pre>
</body>
</html>
```

**Use Cases:**

- Display code snippets
- ASCII art
- Formatted tables (when HTML table is not suitable)
- Poetry with specific line breaks
- Computer output/logs

---

### 8. Spacing: The `<br>` Tag

**The `<br>` Tag** (Line Break)

Creates a **single line break**. It's a self-closing tag (no closing tag needed).

**Syntax:**
```html
<p>First line<br>Second line</p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Line Break Example</title>
</head>
<body>
    <h1>Contact Information</h1>

    <!-- Address with line breaks -->
    <p>
        Tribhuvan University<br>
        Kirtipur, Kathmandu<br>
        Nepal<br>
        Phone: 01-4567890
    </p>

    <h2>Poem</h2>
    <p>
        Roses are red,<br>
        Violets are blue,<br>
        HTML is useful,<br>
        And CSS too!
    </p>

    <h2>Multiple Breaks</h2>
    <p>
        First paragraph.
        <br><br>
        Second paragraph (with double break for more space).
    </p>
</body>
</html>
```

**`<br>` vs `<p>`:**

| Feature | `<br>` | `<p>` |
|---------|---------|-------|
| **Purpose** | Single line break | New paragraph |
| **Space added** | Small (one line) | Larger (paragraph margin) |
| **When to use** | Within same thought | Separate thoughts |
| **Example** | Addresses, poems | Separate ideas |

**Don't Overuse `<br>`:**

❌ **Bad**:
```html
<br><br><br><br>  <!-- Don't use for spacing -->
```

✅ **Good**:
```html
<p style="margin-top: 40px;">  <!-- Use CSS for spacing -->
```

---

### 9. Text Phrases: `<span>`

**The `<span>` Tag**

An **inline container** for text. Has no visual effect by itself but can be styled with CSS or used with JavaScript.

**Syntax:**
```html
<p>This is <span>normal</span> text.</p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Span Example</title>
    <style>
        .highlight {
            background-color: yellow;
            font-weight: bold;
        }
        .red-text {
            color: red;
        }
        .blue-text {
            color: blue;
        }
    </style>
</head>
<body>
    <h1>Using Span for Styling</h1>

    <!-- Highlighting specific words -->
    <p>
        The <span class="highlight">most important</span> thing to remember
        is to practice every day.
    </p>

    <!-- Colored text -->
    <p>
        Nepal's flag has <span class="red-text">red</span> and
        <span class="blue-text">blue</span> colors.
    </p>

    <!-- Multiple spans -->
    <p>
        Temperature: <span class="red-text">35°C</span>,
        Humidity: <span class="blue-text">80%</span>
    </p>
</body>
</html>
```

**Key Points:**

- `<span>` is **inline** (doesn't create new line)
- `<div>` is **block** (creates new line)
- Use `<span>` to style small portions of text

---

### 10. Text Phrases: `<strong>` (Revisited)

**The `<strong>` Tag**

We covered this earlier with `<b>`, but let's see more examples:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Strong Example</title>
</head>
<body>
    <h1>Safety Instructions</h1>

    <p><strong>Warning:</strong> Keep away from children.</p>
    <p><strong>Important:</strong> Read instructions before use.</p>
    <p><strong>Caution:</strong> Hot surface!</p>

    <h2>Exam Instructions</h2>
    <p>
        <strong>Do not</strong> write on the question paper.
        Use the answer sheet provided.
    </p>
</body>
</html>
```

---

### 11. Text Phrases: `<tt>` (Teletype)

**The `<tt>` Tag** (Deprecated but still works)

Displays text in a **monospace font** (like typewriter text).

**Note:** This tag is deprecated in HTML5. Use `<code>`, `<kbd>`, or `<samp>` instead, or use CSS: `font-family: monospace;`

**Old Way (still works):**
```html
<p>Command: <tt>npm install</tt></p>
```

**Modern Alternatives:**

```html
<!-- For code -->
<p>Command: <code>npm install</code></p>

<!-- For keyboard input -->
<p>Press <kbd>Ctrl+C</kbd> to copy</p>

<!-- For sample output -->
<p>Output: <samp>Hello, World!</samp></p>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Monospace Text Example</title>
</head>
<body>
    <h1>Computer Commands</h1>

    <!-- Using <code> for code snippets -->
    <p>To install packages, use: <code>npm install package-name</code></p>

    <!-- Using <kbd> for keyboard shortcuts -->
    <p>Save the file with <kbd>Ctrl+S</kbd></p>
    <p>Undo with <kbd>Ctrl+Z</kbd></p>

    <!-- Using <samp> for program output -->
    <p>The program output is: <samp>Error: File not found</samp></p>

    <!-- Using CSS for monospace -->
    <p>Variable name: <span style="font-family: monospace;">user_name</span></p>
</body>
</html>
```

---

### 12. Comprehensive Formatting Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Complete Formatting Example</title>
    <style>
        .highlight {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <h1>Scientific Article</h1>

    <!-- Combining multiple formatting tags -->
    <p>
        <strong>Abstract:</strong> This paper studies the chemical formula
        H<sub>2</sub>O (water) and Einstein's equation E=mc<sup>2</sup>.
    </p>

    <h2>Introduction</h2>
    <p>
        Water (<i>H<sub>2</sub>O</i>) is <em>essential</em> for life.
        It's composed of <b>two hydrogen atoms</b> and <b>one oxygen atom</b>.
    </p>

    <h2>Mathematical Formula</h2>
    <p>
        The area of a circle is calculated using: <br>
        A = πr<sup>2</sup>
    </p>

    <pre>
        Example calculation:
        If r = 5cm
        Then A = π × 5<sup>2</sup> = 78.54cm<sup>2</sup>
    </pre>

    <h2>Important Notes</h2>
    <p>
        <strong>Remember:</strong> Always <span class="highlight">label your chemicals</span>
        properly. <br>
        Temperature should be measured in degrees Celsius or
        Fahrenheit<sup>*</sup>.
    </p>

    <hr>

    <!-- Footer with small text -->
    <p>
        <small>
            <sup>*</sup>Fahrenheit is commonly used in the United States,
            while Celsius is used in most other countries.
        </small>
    </p>

    <p><small>© 2025 Science Journal. All rights reserved.</small></p>
</body>
</html>
```

---

### 13. Comparison Table: All Formatting Tags

| Tag | Purpose | Semantic? | Example | When to Use |
|-----|---------|-----------|---------|-------------|
| `<b>` | Bold (visual) | No | `<b>bold</b>` | Keywords, product names |
| `<strong>` | Bold (important) | Yes | `<strong>warning</strong>` | Warnings, critical info |
| `<i>` | Italic (visual) | No | `<i>Book Title</i>` | Terms, titles, thoughts |
| `<em>` | Italic (emphasis) | Yes | `<em>really</em>` | Stress, emphasis |
| `<small>` | Smaller text | Yes | `<small>footnote</small>` | Fine print, disclaimers |
| `<sup>` | Superscript | No | `x<sup>2</sup>` | Exponents, footnotes |
| `<sub>` | Subscript | No | `H<sub>2</sub>O` | Chemical formulas |
| `<pre>` | Preformatted | No | `<pre>code</pre>` | Code, ASCII art |
| `<br>` | Line break | No | `Line1<br>Line2` | Addresses, poems |
| `<span>` | Inline container | No | `<span>text</span>` | Styling portions |
| `<code>` | Code snippet | Yes | `<code>var x</code>` | Programming code |
| `<kbd>` | Keyboard input | Yes | `<kbd>Ctrl+C</kbd>` | Keyboard keys |
| `<samp>` | Sample output | Yes | `<samp>Error</samp>` | Computer output |

---

### Summary

**Key Takeaways:**

✅ **`<b>` vs `<strong>`**: Visual bold vs semantic importance
✅ **`<i>` vs `<em>`**: Visual italic vs semantic emphasis
✅ **`<small>`**: Smaller text for fine print
✅ **`<sup>`**: Superscript for exponents (x²)
✅ **`<sub>`**: Subscript for formulas (H₂O)
✅ **`<pre>`**: Preserves spaces and line breaks
✅ **`<br>`**: Single line break
✅ **`<span>`**: Inline container for styling
✅ **Semantic tags are better**: They provide meaning, not just style
✅ **Use CSS for styling**: HTML for structure, CSS for appearance

**Best Practice:** Choose semantic tags (`<strong>`, `<em>`) over presentational tags (`<b>`, `<i>`) when meaning is important!

**Next Steps:**
Now that you understand text formatting, you're ready to learn about images and links—the elements that make web pages interactive and visually appealing!
