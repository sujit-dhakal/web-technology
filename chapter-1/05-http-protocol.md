# Chapter 1: Web Basics - Part 5
## HTTP (HyperText Transfer Protocol)

### What is HTTP?

HTTP (HyperText Transfer Protocol) is the foundation of data communication on the World Wide Web. It's a protocol (set of rules) that defines how messages are formatted and transmitted between web browsers (clients) and web servers.

**Think of it as a language:** Just as humans need to speak the same language to communicate, web browsers and servers use HTTP to understand each other.

**Key Points:**
- **Protocol**: A set of rules for communication
- **Stateless**: Each request is independent (server doesn't remember previous requests)
- **Text-Based**: Messages are readable text (though can carry binary data)
- **Request-Response Model**: Client asks, server answers

### HTTP vs HTTPS

| HTTP | HTTPS |
|------|-------|
| Not encrypted | Encrypted (secure) |
| Port 80 | Port 443 |
| http:// | https:// |
| Data visible | Data protected |
| Not secure for sensitive data | Safe for passwords, credit cards |

**Example:**
- `http://example.com` - Not secure
- `https://example.com` - Secure (padlock icon in browser)

### HTTP Request

When you want to access a web page, your browser sends an HTTP request to the server. This request contains specific information about what you want.

**Components of HTTP Request:**

**1. Request Line**
- Method (GET, POST, etc.)
- URL (what you want)
- HTTP version

**2. Headers**
- Additional information about the request
- Browser details, accepted formats, etc.

**3. Body** (optional)
- Data sent to server (for POST, PUT requests)

**HTTP Request Example:**
```http
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Accept: text/html
Accept-Language: en-US
Connection: keep-alive
```

**Breaking it down:**
- `GET` = I want to retrieve data
- `/index.html` = The specific page I want
- `HTTP/1.1` = I'm using HTTP version 1.1
- `Host` = The website domain
- `User-Agent` = My browser details
- `Accept` = Types of content I can handle
- `Accept-Language` = Preferred language

### HTTP Methods (Verbs)

HTTP defines several methods that specify what action to perform:

| Method | Purpose | Example Use Case |
|--------|---------|------------------|
| **GET** | Retrieve data | Loading a web page, searching |
| **POST** | Send data to create | Submitting a form, creating account |
| **PUT** | Update existing data | Editing profile information |
| **DELETE** | Remove data | Deleting a post |
| **HEAD** | Get headers only | Checking if file exists |
| **PATCH** | Partial update | Updating just email address |
| **OPTIONS** | Ask what methods allowed | API discovery |

**Detailed Examples:**

**1. GET Request** (Most Common)
```http
GET /products?category=electronics&price=low HTTP/1.1
Host: shop.com
```
- Retrieves list of electronics sorted by low price
- Data in URL (visible in address bar)
- Can be bookmarked
- Can be cached

**2. POST Request** (Submitting Forms)
```http
POST /login HTTP/1.1
Host: example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 35

username=john&password=secret123
```
- Sends login credentials
- Data in body (not visible in URL)
- More secure than GET for passwords
- Cannot be bookmarked

**3. Example Scenario:**

**Searching Google (GET):**
```
Browser → GET /search?q=Nepal HTTP/1.1
          Host: www.google.com

Google  → Sends search results page
```

**Logging into Facebook (POST):**
```
Browser → POST /login HTTP/1.1
          Host: www.facebook.com

          email=user@example.com&password=xyz

Facebook → Verifies credentials, creates session
```

### HTTP Response

After the server receives and processes your request, it sends back an HTTP response containing the requested resource or an error message.

**Components of HTTP Response:**

**1. Status Line**
- HTTP version
- Status code
- Status message

**2. Headers**
- Information about the response
- Server details, content type, etc.

**3. Body**
- The actual content (HTML, JSON, image, etc.)

**HTTP Response Example:**
```http
HTTP/1.1 200 OK
Date: Sat, 29 Nov 2025 14:00:00 GMT
Server: Apache/2.4.41
Content-Type: text/html; charset=UTF-8
Content-Length: 1234
Last-Modified: Fri, 28 Nov 2025 10:00:00 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
<head>
    <title>Welcome</title>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

**Breaking it down:**
- `HTTP/1.1 200 OK` = Request successful!
- `Server` = Web server software being used
- `Content-Type` = Type of content (HTML)
- `Content-Length` = Size in bytes
- Body = The actual HTML page

### HTTP Status Codes

Status codes tell you whether the request was successful or what went wrong.

**Categories:**

| Range | Category | Meaning |
|-------|----------|---------|
| 1xx | Informational | Request received, processing |
| 2xx | Success | Request successful |
| 3xx | Redirection | Further action needed |
| 4xx | Client Error | Problem with request |
| 5xx | Server Error | Server failed to fulfill request |

**Common Status Codes:**

**2xx - Success**
- `200 OK` - Request successful, here's your data
- `201 Created` - Successfully created new resource
- `204 No Content` - Success, but nothing to send back

**3xx - Redirection**
- `301 Moved Permanently` - Resource moved to new URL forever
- `302 Found` - Temporarily moved to different URL
- `304 Not Modified` - Use your cached version

**4xx - Client Errors**
- `400 Bad Request` - Invalid request syntax
- `401 Unauthorized` - Need to login first
- `403 Forbidden` - You don't have permission
- `404 Not Found` - Page doesn't exist
- `408 Request Timeout` - Took too long

**5xx - Server Errors**
- `500 Internal Server Error` - Server crashed/error
- `502 Bad Gateway` - Server got invalid response
- `503 Service Unavailable` - Server overloaded/maintenance
- `504 Gateway Timeout` - Server took too long to respond

**Real-World Examples:**

**404 Not Found:**
```
You type: www.example.com/wrongpage

Browser → GET /wrongpage HTTP/1.1
Server  → HTTP/1.1 404 Not Found
          <html><body>Page Not Found</body></html>
```

**301 Redirect:**
```
You type: www.example.com

Browser → GET / HTTP/1.1
Server  → HTTP/1.1 301 Moved Permanently
          Location: https://www.example.com

Browser automatically follows redirect to HTTPS
```

### Complete HTTP Transaction Example

**Scenario:** You want to view your bank balance

**Step 1: You type URL**
```
https://bank.com/account
```

**Step 2: Browser sends request**
```http
GET /account HTTP/1.1
Host: bank.com
User-Agent: Chrome/120.0
Cookie: session_id=abc123xyz
Accept: text/html
```

**Step 3: Server processes request**
- Checks session cookie (are you logged in?)
- Queries database for your account
- Generates HTML with your balance

**Step 4: Server sends response**
```http
HTTP/1.1 200 OK
Server: Nginx/1.18
Content-Type: text/html
Set-Cookie: session_id=abc123xyz; Secure
Content-Length: 2048

<!DOCTYPE html>
<html>
<body>
    <h1>Account Balance</h1>
    <p>Available Balance: Rs. 50,000</p>
</body>
</html>
```

**Step 5: Browser displays page**
- Parses HTML
- Renders balance information
- You see your balance!

### HTTP Headers (Important Ones)

**Request Headers:**
```http
Host: example.com              ← Which website
User-Agent: Mozilla/5.0        ← Browser details
Accept: text/html              ← What formats accepted
Accept-Language: en-US         ← Preferred language
Cookie: user_id=123            ← Previously stored data
Referer: https://google.com    ← Where you came from
Authorization: Bearer token123 ← Authentication token
```

**Response Headers:**
```http
Content-Type: text/html        ← Type of content
Content-Length: 1234           ← Size in bytes
Server: Apache/2.4             ← Server software
Set-Cookie: id=abc; Path=/     ← Store this cookie
Cache-Control: max-age=3600    ← Cache for 1 hour
Location: /newpage             ← Redirect to here
```

### HTTP/1.1 vs HTTP/2 vs HTTP/3

| Feature | HTTP/1.1 | HTTP/2 | HTTP/3 |
|---------|----------|--------|--------|
| Release | 1997 | 2015 | 2020 |
| Protocol | TCP | TCP | UDP |
| Speed | Slower | Faster | Fastest |
| Multiplexing | No | Yes | Yes |
| Header Compression | No | Yes | Yes |
| Adoption | Universal | High | Growing |

**Simple Explanation:**
- **HTTP/1.1**: One request at a time (like single-lane road)
- **HTTP/2**: Multiple requests simultaneously (multi-lane highway)
- **HTTP/3**: Even faster, better for mobile (supersonic highway)

### Summary

**HTTP** is the protocol that powers the web:
- **Request**: Client asks for resources
- **Response**: Server provides resources
- **Methods**: GET (retrieve), POST (send), PUT (update), DELETE (remove)
- **Status Codes**: Tell you what happened (200=success, 404=not found, 500=error)
- **Stateless**: Each request is independent
- **HTTPS**: Secure version with encryption

Every time you browse the web, HTTP is working behind the scenes to deliver content to you!
