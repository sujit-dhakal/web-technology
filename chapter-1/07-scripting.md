# Chapter 1: Web Basics - Part 7
## Client-Side and Server-Side Scripting

### What is Scripting?

Scripting refers to writing small programs (scripts) that automate tasks or add interactivity to web pages. In web development, scripts can run either on the client (user's browser) or on the server.

### Client-Side Scripting

**What is Client-Side Scripting?**

Client-side scripting involves code that runs in the user's web browser. The server sends the script to the browser, and the browser executes it locally on the user's device.

**Primary Language: JavaScript**

**Key Characteristics:**
- ✅ Runs in the browser (Chrome, Firefox, Safari)
- ✅ Executes on user's computer
- ✅ Code is visible to users (View Source)
- ✅ No server round-trip needed
- ✅ Fast and responsive
- ✅ Reduces server load

**Technologies:**
1. **JavaScript** (primary language)
2. **HTML5 APIs** (Geolocation, Local Storage)
3. **CSS** (for styling, animations)
4. **TypeScript** (compiles to JavaScript)

**What Can Client-Side Scripts Do?**

**1. Form Validation**
```html
<!DOCTYPE html>
<html>
<body>
    <form onsubmit="return validateForm()">
        Email: <input type="text" id="email">
        <button type="submit">Submit</button>
    </form>

    <script>
    function validateForm() {
        var email = document.getElementById('email').value;

        if (email.indexOf('@') === -1) {
            alert('Please enter a valid email!');
            return false;  // Prevent form submission
        }
        return true;  // Allow submission
    }
    </script>
</body>
</html>
```
*Before sending data to server, check if it's valid*

**2. Dynamic Content**
```html
<button onclick="changeContent()">Click Me</button>
<p id="demo">Original text</p>

<script>
function changeContent() {
    document.getElementById('demo').innerHTML = 'Text changed!';
}
</script>
```
*Change page content without reloading*

**3. Animations and Effects**
```html
<div id="box" style="width:100px; height:100px; background:blue;"></div>

<script>
// Move the box
var box = document.getElementById('box');
var position = 0;

setInterval(function() {
    position += 1;
    box.style.marginLeft = position + 'px';
}, 10);
</script>
```
*Create visual animations*

**4. User Interactions**
```javascript
// Display current time
function showTime() {
    var now = new Date();
    var timeString = now.toLocaleTimeString();
    document.getElementById('clock').innerHTML = timeString;
}
setInterval(showTime, 1000);  // Update every second
```

**5. AJAX (Asynchronous Requests)**
```javascript
// Load data without page reload
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
        console.log(data);
        // Update page with new data
    });
```

**Real-World Examples:**

| Website | Client-Side Scripting Use |
|---------|---------------------------|
| **Google Maps** | Pan, zoom, get directions without reload |
| **Facebook** | Infinite scroll, like posts instantly |
| **Gmail** | Read emails, compose without page reload |
| **Netflix** | Preview videos on hover |
| **Twitter** | Real-time tweet updates |

**Advantages:**
- ✅ Fast response (no server wait)
- ✅ Better user experience
- ✅ Reduces server load
- ✅ Works offline (once loaded)
- ✅ Interactive features

**Disadvantages:**
- ❌ Code is visible (security risk)
- ❌ Can be disabled by user
- ❌ Different browsers may behave differently
- ❌ Cannot access server resources directly
- ❌ Limited to browser capabilities

### Server-Side Scripting

**What is Server-Side Scripting?**

Server-side scripting involves code that runs on the web server before sending the response to the client. The server processes the script and sends only the output (usually HTML) to the browser.

**Popular Languages:**
1. **PHP** (most popular for web)
2. **Python** (Django, Flask frameworks)
3. **Java** (JSP, Servlets)
4. **Node.js** (JavaScript on server)
5. **Ruby** (Ruby on Rails)
6. **C#** (ASP.NET)

**Key Characteristics:**
- ✅ Runs on the server
- ✅ Code is hidden from users
- ✅ Can access databases
- ✅ Can process files on server
- ✅ More secure
- ✅ Consistent across all browsers

**What Can Server-Side Scripts Do?**

**1. Database Operations**
```php
<?php
// Connect to database
$conn = mysqli_connect("localhost", "user", "pass", "database");

// Get user data
$user_id = $_GET['id'];
$query = "SELECT * FROM users WHERE id = $user_id";
$result = mysqli_query($conn, $query);
$user = mysqli_fetch_assoc($result);

// Display user information
echo "<h1>Welcome, " . $user['name'] . "</h1>";
echo "<p>Email: " . $user['email'] . "</p>";
?>
```
*Server retrieves data from database*

**2. User Authentication**
```php
<?php
// Login processing
$username = $_POST['username'];
$password = $_POST['password'];

// Check credentials in database
$query = "SELECT * FROM users WHERE username='$username'";
$result = mysqli_query($conn, $query);

if ($result && password_verify($password, $user['password_hash'])) {
    // Login successful
    session_start();
    $_SESSION['user_id'] = $user['id'];
    header('Location: dashboard.php');
} else {
    echo "Invalid credentials!";
}
?>
```
*Server verifies login credentials*

**3. Dynamic Page Generation**
```php
<?php
// Generate different content based on time
$hour = date('H');

if ($hour < 12) {
    $greeting = "Good Morning";
} elseif ($hour < 18) {
    $greeting = "Good Afternoon";
} else {
    $greeting = "Good Evening";
}

echo "<h1>$greeting, User!</h1>";

// Get and display latest news from database
$news_query = "SELECT * FROM news ORDER BY date DESC LIMIT 5";
$news_result = mysqli_query($conn, $news_query);

while ($article = mysqli_fetch_assoc($news_result)) {
    echo "<h2>" . $article['title'] . "</h2>";
    echo "<p>" . $article['content'] . "</p>";
}
?>
```
*Server creates customized page*

**4. File Handling**
```php
<?php
// Upload file to server
if (isset($_FILES['document'])) {
    $file = $_FILES['document'];
    $filename = $file['name'];
    $temp_path = $file['tmp_name'];
    $destination = 'uploads/' . $filename;

    if (move_uploaded_file($temp_path, $destination)) {
        echo "File uploaded successfully!";
        // Save file info to database
        $query = "INSERT INTO files (filename, path) VALUES ('$filename', '$destination')";
        mysqli_query($conn, $query);
    }
}
?>
```
*Server processes file uploads*

**5. Email Sending**
```php
<?php
// Send email
$to = "user@example.com";
$subject = "Welcome to Our Website";
$message = "Thank you for registering!";
$headers = "From: noreply@oursite.com";

mail($to, $subject, $message, $headers);
echo "Email sent!";
?>
```
*Server sends emails*

**Real-World Examples:**

| Website | Server-Side Scripting Use |
|---------|---------------------------|
| **Facebook** | Process logins, store posts, friends |
| **Amazon** | Process orders, payments, inventory |
| **Gmail** | Store emails, send/receive messages |
| **YouTube** | Process video uploads, store comments |
| **Banking Sites** | Process transactions, check balance |

**Advantages:**
- ✅ More secure (code hidden)
- ✅ Can access databases
- ✅ Can perform complex operations
- ✅ Works on all browsers the same
- ✅ Can handle file operations
- ✅ Can integrate with other services

**Disadvantages:**
- ❌ Slower (server processing + network)
- ❌ Requires server resources
- ❌ Page reload often needed
- ❌ More expensive (server costs)
- ❌ Server can get overloaded

### Comparison: Client-Side vs Server-Side

| Aspect | Client-Side | Server-Side |
|--------|-------------|-------------|
| **Runs On** | User's browser | Web server |
| **Language** | JavaScript (mainly) | PHP, Python, Java, etc. |
| **Speed** | Fast (no network) | Slower (network delay) |
| **Security** | Less secure (code visible) | More secure (code hidden) |
| **Database Access** | No | Yes |
| **Processing Power** | Limited (user's device) | Powerful (server) |
| **Browser Dependency** | Yes | No |
| **Examples** | Form validation, animations | Login, database queries |
| **When to Use** | UI interactions, validation | Data processing, security |

### How They Work Together

Modern websites use **both** client-side and server-side scripting for optimal performance:

**Example: User Registration**

```
Step 1: User fills form
   ↓
Step 2: CLIENT-SIDE validates fields
   - Check if email format correct
   - Check if password strong enough
   - Check if all fields filled
   ↓
Step 3: If valid, submit to server
   ↓
Step 4: SERVER-SIDE processes
   - Check if email already exists in database
   - Hash password for security
   - Insert user into database
   - Send confirmation email
   ↓
Step 5: Server sends response
   ↓
Step 6: CLIENT-SIDE displays success message
```

**Code Example:**

**Client-Side (JavaScript):**
```html
<form onsubmit="return validateForm()">
    Email: <input type="email" id="email">
    Password: <input type="password" id="password">
    <button type="submit">Register</button>
</form>

<script>
function validateForm() {
    var email = document.getElementById('email').value;
    var password = document.getElementById('password').value;

    // Client-side validation
    if (password.length < 8) {
        alert('Password must be at least 8 characters!');
        return false;
    }

    if (email.indexOf('@') === -1) {
        alert('Invalid email!');
        return false;
    }

    return true;  // Submit to server
}
</script>
```

**Server-Side (PHP):**
```php
<?php
// Receive data from client
$email = $_POST['email'];
$password = $_POST['password'];

// Server-side validation (backup)
if (strlen($password) < 8) {
    die('Password too short!');
}

// Check if email exists
$query = "SELECT * FROM users WHERE email='$email'";
$result = mysqli_query($conn, $query);

if (mysqli_num_rows($result) > 0) {
    die('Email already registered!');
}

// Hash password
$hashed_password = password_hash($password, PASSWORD_DEFAULT);

// Insert into database
$query = "INSERT INTO users (email, password) VALUES ('$email', '$hashed_password')";
mysqli_query($conn, $query);

// Send confirmation email
mail($email, "Welcome", "Registration successful!");

echo "Registration complete!";
?>
```

### Visual Representation

```
┌─────────────────────────────────────┐
│         WEB BROWSER (CLIENT)        │
│                                     │
│  ┌───────────────────────────────┐ │
│  │   Client-Side Scripting       │ │
│  │   (JavaScript)                │ │
│  │                               │ │
│  │   • Form validation           │ │
│  │   • Animations                │ │
│  │   • UI interactions           │ │
│  │   • AJAX requests             │ │
│  └───────────────────────────────┘ │
└──────────────┬──────────────────────┘
               │ HTTP Request
               ▼
┌──────────────────────────────────────┐
│         WEB SERVER                    │
│                                       │
│  ┌─────────────────────────────────┐ │
│  │   Server-Side Scripting         │ │
│  │   (PHP/Python/Java)             │ │
│  │                                 │ │
│  │   • Database operations         │ │
│  │   • Authentication              │ │
│  │   • File processing             │ │
│  │   • Business logic              │ │
│  └─────────────────────────────────┘ │
│               │                       │
│  ┌────────────▼──────────────────┐   │
│  │   DATABASE                    │   │
│  │   (MySQL/PostgreSQL)          │   │
│  └───────────────────────────────┘   │
└───────────────────────────────────────┘
```

### Summary

**Client-Side Scripting:**
- Runs in browser (JavaScript)
- Fast and interactive
- Handles UI and validation
- Code is visible
- Limited to browser capabilities

**Server-Side Scripting:**
- Runs on server (PHP, Python, etc.)
- Secure and powerful
- Handles data and business logic
- Code is hidden
- Can access databases and files

**Best Practice:** Use both together—client-side for speed and UX, server-side for security and data management!
