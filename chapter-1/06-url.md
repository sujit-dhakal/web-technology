# Chapter 1: Web Basics - Part 6
## URL (Uniform Resource Locator)

### What is a URL?

A URL (Uniform Resource Locator) is the address of a specific webpage or file on the Internet. It's what you type in your browser's address bar to visit a website. Think of it as a postal address for web resources.

**Example URLs:**
- `https://www.google.com`
- `https://www.facebook.com/profile`
- `https://shop.com/products?category=electronics#reviews`

### Anatomy of a URL

A URL consists of several parts, each serving a specific purpose:

```
https://www.example.com:443/path/to/page?key=value&name=john#section2
└─┬─┘  └──────┬──────┘ └┬┘ └────┬────┘ └───────┬───────┘ └───┬───┘
  │           │         │       │              │              │
Scheme      Domain     Port    Path          Query        Fragment
(Protocol)   (Host)                         (Parameters)   (Anchor)
```

Let's break down each part:

### 1. Scheme (Protocol)

The scheme specifies which protocol to use to access the resource.

**Common Schemes:**
- `http://` - HyperText Transfer Protocol
- `https://` - HTTP Secure (encrypted)
- `ftp://` - File Transfer Protocol
- `mailto:` - Email address
- `file://` - Local file on your computer

**Examples:**
```
https://example.com     ← Secure website
http://example.com      ← Non-secure website
ftp://files.example.com ← File transfer
mailto:info@example.com ← Email link
```

**Real-World Analogy:** Think of the scheme as the mode of transportation—car, bus, or airplane—each has different rules and capabilities.

### 2. Domain Name (Host)

The domain name identifies which server on the Internet hosts the resource.

**Parts of a Domain:**
```
www.example.com
└┬┘ └──┬──┘ └┬┘
 │     │     │
Sub   Domain  TLD
domain Name   (Top Level Domain)
```

**Subdomain:** (optional)
- `www` - World Wide Web (most common)
- `mail` - Email service
- `blog` - Blog section
- `shop` - Shopping section

**Domain Name:**
- The unique name identifying the website
- Must be registered and unique
- Examples: `google`, `facebook`, `youtube`

**Top-Level Domain (TLD):**
- `.com` - Commercial
- `.org` - Organization
- `.edu` - Educational
- `.gov` - Government
- `.np` - Nepal
- `.in` - India
- `.uk` - United Kingdom

**Examples:**
```
www.google.com
mail.google.com
docs.google.com
drive.google.com
```

**IP Address Alternative:**
Instead of domain names, you can use IP addresses:
```
http://142.250.183.206  ← Google's IP address
```
But domain names are easier to remember!

### 3. Port Number

The port number specifies which "door" to use on the server. It's usually optional because default ports are assumed.

**Default Ports:**
- HTTP: Port 80 (usually omitted)
- HTTPS: Port 443 (usually omitted)
- FTP: Port 21

**Examples:**
```
http://example.com:80     ← Same as http://example.com
https://example.com:443   ← Same as https://example.com
http://localhost:3000     ← Development server (custom port)
http://example.com:8080   ← Alternative HTTP port
```

**When to specify:**
- Development environments
- Non-standard configurations
- Specific services

### 4. Path

The path specifies the specific resource or page on the server. It's like folders and files on your computer.

**Examples:**
```
https://shop.com/products/electronics/laptops
                └────────┬─────────┘
                      Path
```

**Breaking it down:**
```
/                       ← Homepage/root
/about                  ← About page
/products               ← Products listing
/products/electronics   ← Electronics category
/users/john/profile     ← John's profile page
```

**File Extensions:**
```
/images/photo.jpg       ← JPEG image
/documents/manual.pdf   ← PDF document
/styles/main.css        ← CSS stylesheet
/scripts/app.js         ← JavaScript file
```

**Real-World Analogy:** Think of the path as directions within a building—first floor, room 101, drawer 3.

### 5. Query String (Parameters)

The query string passes additional data to the server. It starts with `?` and contains key-value pairs separated by `&`.

**Format:**
```
?key1=value1&key2=value2&key3=value3
```

**Examples:**
```
https://shop.com/products?category=electronics&price=low&brand=samsung

Breaking it down:
category=electronics  ← Filter by category
price=low            ← Sort by low price
brand=samsung        ← Filter by brand
```

**Real-World Examples:**

**Google Search:**
```
https://www.google.com/search?q=Nepal
                                └─┬─┘
                               Search query
```

**YouTube Video:**
```
https://www.youtube.com/watch?v=dQw4w9WgXcQ
                               └────┬────┘
                              Video ID
```

**E-commerce Filtering:**
```
https://shop.com/search?query=laptop&min=50000&max=100000&sort=popular

query=laptop     ← Search term
min=50000        ← Minimum price
max=100000       ← Maximum price
sort=popular     ← Sort by popularity
```

**Pagination:**
```
https://blog.com/posts?page=2&limit=10

page=2    ← Show page 2
limit=10  ← Show 10 items per page
```

### 6. Fragment (Anchor)

The fragment identifies a specific section within a page. It starts with `#` and is processed by the browser, not sent to the server.

**Examples:**
```
https://example.com/article#introduction
https://example.com/page#section2
https://example.com/faq#question-5
```

**How it works:**
```html
<!-- HTML page with sections -->
<h1 id="introduction">Introduction</h1>
<p>Content here...</p>

<h2 id="section2">Section 2</h2>
<p>More content...</p>

<!-- Links to sections -->
<a href="#introduction">Go to Introduction</a>
<a href="#section2">Go to Section 2</a>
```

When you click, the browser scrolls to that section without reloading the page!

**Real-World Use:**
```
https://en.wikipedia.org/wiki/Nepal#History
                                    └──┬──┘
                              Jumps to History section
```

### Complete URL Examples

**Example 1: Simple Website**
```
https://www.example.com

Scheme: https
Domain: www.example.com
Port: 443 (default, not shown)
Path: / (root, not shown)
```

**Example 2: E-commerce Product**
```
https://shop.com/products/laptop?brand=dell&color=black#specifications

Scheme: https
Domain: shop.com
Path: /products/laptop
Query: brand=dell&color=black
Fragment: #specifications
```

**Example 3: Local Development**
```
http://localhost:3000/admin/users?role=editor&status=active

Scheme: http
Domain: localhost (your computer)
Port: 3000
Path: /admin/users
Query: role=editor&status=active
```

### URL Encoding

Some characters have special meanings in URLs, so they must be encoded.

**Special Characters:**
```
Space    → %20 or +
?        → %3F
&        → %26
=        → %3D
/        → %2F
#        → %23
```

**Example:**
```
Original: https://example.com/search?q=web development
Encoded:  https://example.com/search?q=web%20development

Original: https://example.com/file?name=report&data.pdf
Encoded:  https://example.com/file?name=report%26data.pdf
```

### Absolute vs Relative URLs

**Absolute URL:**
Complete address including scheme and domain.
```html
<a href="https://www.example.com/about">About Us</a>
```
- Works from anywhere
- Complete and independent

**Relative URL:**
Address relative to current page location.
```html
<!-- If you're on https://example.com/products/ -->
<a href="laptops">Laptops</a>
<!-- Goes to https://example.com/products/laptops -->

<a href="/contact">Contact</a>
<!-- Goes to https://example.com/contact -->

<a href="../home">Home</a>
<!-- Goes up one level, then to home -->
```

**Comparison:**

| Type | Example | Use Case |
|------|---------|----------|
| Absolute | `https://example.com/page` | External links |
| Relative | `/page` or `page` | Internal navigation |

### Real-World Examples

**1. Search Engine:**
```
https://www.google.com/search?q=web+development&hl=en&gl=us

- Search for "web development"
- Language: English (hl=en)
- Country: United States (gl=us)
```

**2. Social Media Profile:**
```
https://www.facebook.com/zuckerberg

- Facebook's domain
- User: zuckerberg
```

**3. Video with Timestamp:**
```
https://www.youtube.com/watch?v=dQw4w9WgXcQ&t=30s

- Video ID: dQw4w9WgXcQ
- Start at 30 seconds (t=30s)
```

**4. E-commerce with Filters:**
```
https://www.daraz.com.np/catalog/?q=shoes&price=1000-5000&rating=4

- Search: shoes
- Price range: 1000-5000
- Rating: 4 stars and above
```

### Common URL Patterns

**Homepage:**
```
https://example.com
https://example.com/
```

**Blog Post:**
```
https://blog.com/2025/11/my-first-post
https://blog.com/posts/123
```

**User Profile:**
```
https://twitter.com/username
https://github.com/username
```

**API Endpoint:**
```
https://api.example.com/v1/users/123
https://api.example.com/products?limit=10
```

### Best Practices for URLs

✅ **Good URLs:**
- `https://shop.com/products/laptops`
- `https://blog.com/how-to-learn-web-development`
- `https://university.edu/courses/computer-science`

❌ **Bad URLs:**
- `http://example.com/page.php?id=123&cat=45&user=xyz`
- `http://site.com/index.html?sessionid=abc123def456`
- `http://example.com/~user/files/docs/file(1).pdf`

**Characteristics of Good URLs:**
- Short and memorable
- Descriptive and meaningful
- Use hyphens, not underscores
- Lowercase letters
- HTTPS (secure)
- No unnecessary parameters

### Summary

A **URL** is the complete address of a web resource, consisting of:
- **Scheme**: Protocol to use (http, https)
- **Domain**: Server address (www.example.com)
- **Port**: Connection point (80, 443)
- **Path**: Specific resource (/products/laptop)
- **Query**: Additional parameters (?id=123)
- **Fragment**: Page section (#introduction)

URLs are the foundation of web navigation, allowing us to locate and access any resource on the Internet!
