# Chapter 2: Introduction to HTML - Part 8
## Forms and Form Elements

### 1. Introduction to HTML Forms

**What are HTML Forms?**

Forms are used to collect user input on websites. They're the primary way users communicate with web servers - like filling out a registration form, logging in, searching, or submitting feedback.

**Real-World Analogy:**

Think of an HTML form like a physical form you fill out at a bank or hospital - you provide information in different fields (text boxes, checkboxes), and then submit it for processing.

**Common Form Examples:**

- Login page (username, password)
- Registration/signup
- Contact form (name, email, message)
- Search box
- Survey/questionnaire
- Online shopping checkout

---

### 2. Basic Form Structure

**The `<form>` Element:**

```html
<form action="process.php" method="POST">
    <!-- Form elements go here -->
    <input type="text" name="username">
    <input type="submit" value="Submit">
</form>
```

**Form Attributes:**

| Attribute | Purpose | Values/Example |
|-----------|---------|----------------|
| `action` | Where to send form data | URL: `action="submit.php"` |
| `method` | How to send data | `GET` or `POST` |
| `name` | Form identifier | `name="loginform"` |
| `target` | Where to display response | `_self`, `_blank` |
| `enctype` | Encoding type (for file uploads) | `multipart/form-data` |

---

### 3. GET vs POST Methods

**GET Method:**

```html
<form action="search.php" method="GET">
    <input type="text" name="query">
    <input type="submit" value="Search">
</form>
```

**Characteristics:**
- Data appears in URL: `search.php?query=html+tutorial`
- Limited data size (~2000 characters)
- Data is visible (not secure for passwords)
- Can be bookmarked
- Good for searches, filters

**POST Method:**

```html
<form action="login.php" method="POST">
    <input type="text" name="username">
    <input type="password" name="password">
    <input type="submit" value="Login">
</form>
```

**Characteristics:**
- Data sent in request body (not in URL)
- No size limit
- More secure
- Cannot be bookmarked
- Good for sensitive data, file uploads

**Comparison:**

| Feature | GET | POST |
|---------|-----|------|
| **Visibility** | Visible in URL | Hidden |
| **Security** | Less secure | More secure |
| **Data Size** | Limited (~2KB) | Unlimited |
| **Bookmarkable** | Yes | No |
| **Use Case** | Search, filters | Login, registration |

---

### 4. Text Input Fields

**Single-Line Text Input:**

```html
<input type="text" name="fieldname" value="default" placeholder="Enter text...">
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Text Input Example</title>
</head>
<body>
    <h1>User Information Form</h1>

    <form action="submit.php" method="POST">
        <!-- Basic text input -->
        <label for="firstname">First Name:</label>
        <input type="text" id="firstname" name="firstname" placeholder="John">
        <br><br>

        <!-- Text input with default value -->
        <label for="country">Country:</label>
        <input type="text" id="country" name="country" value="Nepal">
        <br><br>

        <!-- Required field -->
        <label for="email">Email (required):</label>
        <input type="text" id="email" name="email" required>
        <br><br>

        <!-- Read-only field -->
        <label for="userid">User ID:</label>
        <input type="text" id="userid" name="userid" value="12345" readonly>
        <br><br>

        <!-- Disabled field -->
        <label for="status">Status:</label>
        <input type="text" id="status" name="status" value="Active" disabled>
        <br><br>

        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**Text Input Attributes:**

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `name` | Field identifier | `name="username"` |
| `value` | Default value | `value="John"` |
| `placeholder` | Hint text | `placeholder="Enter name"` |
| `required` | Must be filled | `required` |
| `readonly` | Can't modify | `readonly` |
| `disabled` | Grayed out, not submitted | `disabled` |
| `maxlength` | Max characters | `maxlength="50"` |
| `size` | Visible width | `size="30"` |

---

### 5. Password Input

**Password Field:**

```html
<input type="password" name="password" placeholder="Enter password">
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Login Form</title>
</head>
<body>
    <h1>Login</h1>

    <form action="login.php" method="POST">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
        <br><br>

        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required minlength="8">
        <br><br>

        <input type="submit" value="Login">
    </form>
</body>
</html>
```

**Note:** Password fields display • or * instead of actual characters.

---

### 6. Email, Number, and Other HTML5 Input Types

**Email Input:**

```html
<input type="email" name="email" placeholder="user@example.com">
```

**Number Input:**

```html
<input type="number" name="age" min="1" max="120" step="1">
```

**Example with Various Types:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML5 Input Types</title>
</head>
<body>
    <h1>Registration Form</h1>

    <form action="register.php" method="POST">
        <!-- Email -->
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <br><br>

        <!-- Number -->
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" min="18" max="100">
        <br><br>

        <!-- Date -->
        <label for="dob">Date of Birth:</label>
        <input type="date" id="dob" name="dob">
        <br><br>

        <!-- Time -->
        <label for="appointment">Appointment Time:</label>
        <input type="time" id="appointment" name="appointment">
        <br><br>

        <!-- URL -->
        <label for="website">Website:</label>
        <input type="url" id="website" name="website" placeholder="https://example.com">
        <br><br>

        <!-- Tel (Phone) -->
        <label for="phone">Phone:</label>
        <input type="tel" id="phone" name="phone" pattern="[0-9]{10}" placeholder="9841234567">
        <br><br>

        <!-- Color -->
        <label for="favcolor">Favorite Color:</label>
        <input type="color" id="favcolor" name="favcolor" value="#ff0000">
        <br><br>

        <!-- Range (Slider) -->
        <label for="volume">Volume:</label>
        <input type="range" id="volume" name="volume" min="0" max="100" value="50">
        <br><br>

        <input type="submit" value="Register">
    </form>
</body>
</html>
```

**HTML5 Input Types Summary:**

| Type | Purpose | Example |
|------|---------|---------|
| `email` | Email address validation | `<input type="email">` |
| `number` | Numeric input | `<input type="number" min="1" max="10">` |
| `date` | Date picker | `<input type="date">` |
| `time` | Time picker | `<input type="time">` |
| `url` | URL validation | `<input type="url">` |
| `tel` | Phone number | `<input type="tel">` |
| `color` | Color picker | `<input type="color">` |
| `range` | Slider | `<input type="range" min="0" max="100">` |
| `search` | Search box | `<input type="search">` |

---

### 7. Checkboxes

**Checkbox Input:**

```html
<input type="checkbox" name="interest" value="sports"> Sports
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Checkbox Example</title>
</head>
<body>
    <h1>Select Your Interests</h1>

    <form action="submit.php" method="POST">
        <label>Hobbies:</label><br>

        <input type="checkbox" name="hobby[]" value="reading" id="reading">
        <label for="reading">Reading</label><br>

        <input type="checkbox" name="hobby[]" value="sports" id="sports" checked>
        <label for="sports">Sports (pre-selected)</label><br>

        <input type="checkbox" name="hobby[]" value="music" id="music">
        <label for="music">Music</label><br>

        <input type="checkbox" name="hobby[]" value="travel" id="travel">
        <label for="travel">Travel</label><br>

        <br>

        <input type="checkbox" name="subscribe" id="subscribe" value="yes">
        <label for="subscribe">Subscribe to newsletter</label><br>

        <br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**Key Points:**
- `checked` attribute pre-selects checkbox
- Multiple checkboxes can be selected
- Use `name="field[]"` for multiple values

---

### 8. Radio Buttons

**Radio Input:**

```html
<input type="radio" name="gender" value="male"> Male
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Radio Button Example</title>
</head>
<body>
    <h1>Survey Form</h1>

    <form action="survey.php" method="POST">
        <label>Gender:</label><br>
        <input type="radio" name="gender" value="male" id="male">
        <label for="male">Male</label><br>

        <input type="radio" name="gender" value="female" id="female" checked>
        <label for="female">Female (pre-selected)</label><br>

        <input type="radio" name="gender" value="other" id="other">
        <label for="other">Other</label><br>

        <br>

        <label>Experience Level:</label><br>
        <input type="radio" name="experience" value="beginner" id="beginner">
        <label for="beginner">Beginner</label><br>

        <input type="radio" name="experience" value="intermediate" id="intermediate">
        <label for="intermediate">Intermediate</label><br>

        <input type="radio" name="experience" value="advanced" id="advanced">
        <label for="advanced">Advanced</label><br>

        <br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**Key Difference: Checkbox vs Radio:**

| Feature | Checkbox | Radio |
|---------|----------|-------|
| **Selection** | Multiple | Single (one from group) |
| **Name** | Can be different | Must be same for group |
| **Use Case** | Select multiple options | Choose one option |
| **Example** | Select hobbies | Choose gender |

---

### 9. Dropdown Lists (Select)

**Select Element:**

```html
<select name="country">
    <option value="nepal">Nepal</option>
    <option value="india">India</option>
</select>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Dropdown Example</title>
</head>
<body>
    <h1>Registration Form</h1>

    <form action="register.php" method="POST">
        <!-- Single selection dropdown -->
        <label for="country">Country:</label>
        <select name="country" id="country">
            <option value="">-- Select Country --</option>
            <option value="nepal" selected>Nepal</option>
            <option value="india">India</option>
            <option value="china">China</option>
            <option value="bhutan">Bhutan</option>
        </select>
        <br><br>

        <!-- Grouped options -->
        <label for="subject">Favorite Subject:</label>
        <select name="subject" id="subject">
            <optgroup label="Science">
                <option value="physics">Physics</option>
                <option value="chemistry">Chemistry</option>
                <option value="biology">Biology</option>
            </optgroup>
            <optgroup label="Arts">
                <option value="history">History</option>
                <option value="geography">Geography</option>
                <option value="literature">Literature</option>
            </optgroup>
        </select>
        <br><br>

        <!-- Multiple selection -->
        <label for="languages">Languages (hold Ctrl to select multiple):</label>
        <select name="languages[]" id="languages" multiple size="4">
            <option value="nepali">Nepali</option>
            <option value="english">English</option>
            <option value="hindi">Hindi</option>
            <option value="newari">Newari</option>
        </select>
        <br><br>

        <input type="submit" value="Register">
    </form>
</body>
</html>
```

---

### 10. Textarea (Multi-line Text)

**Textarea Element:**

```html
<textarea name="message" rows="5" cols="40">Default text</textarea>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Textarea Example</title>
</head>
<body>
    <h1>Contact Form</h1>

    <form action="contact.php" method="POST">
        <label for="name">Name:</label><br>
        <input type="text" id="name" name="name" required>
        <br><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" required>
        <br><br>

        <label for="message">Message:</label><br>
        <textarea id="message" name="message" rows="6" cols="50" placeholder="Enter your message here..." required></textarea>
        <br><br>

        <input type="submit" value="Send Message">
    </form>
</body>
</html>
```

**Textarea Attributes:**

- `rows` - Number of visible text lines
- `cols` - Width in characters
- `placeholder` - Hint text
- `required` - Must be filled
- `maxlength` - Maximum characters

---

### 11. Buttons

**Types of Buttons:**

```html
<!-- Submit button (submits form) -->
<input type="submit" value="Submit">
<button type="submit">Submit Form</button>

<!-- Reset button (clears form) -->
<input type="reset" value="Reset">
<button type="reset">Clear Form</button>

<!-- Regular button (for JavaScript) -->
<input type="button" value="Click Me" onclick="alert('Clicked!')">
<button type="button" onclick="doSomething()">Click Me</button>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Button Types</title>
</head>
<body>
    <h1>Button Examples</h1>

    <form action="submit.php" method="POST">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username">
        <br><br>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email">
        <br><br>

        <!-- Submit button -->
        <button type="submit">Submit Form</button>

        <!-- Reset button -->
        <button type="reset">Reset Form</button>

        <!-- Regular button -->
        <button type="button" onclick="alert('This is a regular button!')">Info</button>
    </form>
</body>
</html>
```

---

### 12. File Upload

**File Input:**

```html
<form action="upload.php" method="POST" enctype="multipart/form-data">
    <input type="file" name="uploadfile">
    <input type="submit" value="Upload">
</form>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>File Upload</title>
</head>
<body>
    <h1>Upload Your Document</h1>

    <form action="upload.php" method="POST" enctype="multipart/form-data">
        <label for="document">Choose file:</label>
        <input type="file" id="document" name="document" accept=".pdf,.doc,.docx">
        <br><br>

        <!-- Multiple files -->
        <label for="photos">Upload photos (multiple):</label>
        <input type="file" id="photos" name="photos[]" multiple accept="image/*">
        <br><br>

        <input type="submit" value="Upload Files">
    </form>
</body>
</html>
```

**Important:** Must use `method="POST"` and `enctype="multipart/form-data"` for file uploads!

---

### 13. Hidden Fields

**Hidden Input:**

```html
<input type="hidden" name="userid" value="12345">
```

**Example:**

```html
<form action="update.php" method="POST">
    <!-- Visible fields -->
    <label for="username">Update Username:</label>
    <input type="text" id="username" name="username">
    <br><br>

    <!-- Hidden field (user doesn't see this) -->
    <input type="hidden" name="userid" value="<?php echo $user_id; ?>">
    <input type="hidden" name="action" value="update_profile">

    <input type="submit" value="Update">
</form>
```

**Use Cases:**
- Store user ID
- Track form state
- Pass data between pages

---

### 14. Labels and Accessibility

**Why Use `<label>`?**

1. **Accessibility**: Screen readers can associate label with input
2. **Usability**: Clicking label focuses the input
3. **Better UX**: Larger click area

**Two Ways to Use Labels:**

```html
<!-- Method 1: Using 'for' attribute -->
<label for="username">Username:</label>
<input type="text" id="username" name="username">

<!-- Method 2: Wrapping -->
<label>
    Username:
    <input type="text" name="username">
</label>
```

---

### 15. ID and Class Attributes

**ID Attribute:**

```html
<input type="text" id="unique-field" name="field">
```

- Must be **unique** on the page
- Used for JavaScript/CSS targeting
- Used with `<label for="id">`

**Class Attribute:**

```html
<input type="text" class="required-field" name="field1">
<input type="text" class="required-field" name="field2">
```

- Can be **reused** multiple times
- Used for styling groups of elements

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>ID and Class Example</title>
    <style>
        .required-field {
            border: 2px solid red;
        }
        .optional-field {
            border: 1px solid gray;
        }
        #submit-btn {
            background-color: green;
            color: white;
            padding: 10px 20px;
        }
    </style>
</head>
<body>
    <h1>Form with ID and Class</h1>

    <form>
        <label for="name">Name (required):</label>
        <input type="text" id="name" name="name" class="required-field">
        <br><br>

        <label for="email">Email (required):</label>
        <input type="email" id="email" name="email" class="required-field">
        <br><br>

        <label for="phone">Phone (optional):</label>
        <input type="tel" id="phone" name="phone" class="optional-field">
        <br><br>

        <button type="submit" id="submit-btn">Submit</button>
    </form>
</body>
</html>
```

---

### 16. Complete Registration Form Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>User Registration</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 500px; margin: 50px auto; padding: 20px; }
        .form-group { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="date"],
        select,
        textarea {
            width: 100%;
            padding: 8px;
            box-sizing: border-box;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .submit-btn {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .submit-btn:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>User Registration Form</h1>

    <form action="register.php" method="POST" enctype="multipart/form-data">
        <!-- Personal Information -->
        <fieldset>
            <legend>Personal Information</legend>

            <div class="form-group">
                <label for="firstname">First Name: *</label>
                <input type="text" id="firstname" name="firstname" required>
            </div>

            <div class="form-group">
                <label for="lastname">Last Name: *</label>
                <input type="text" id="lastname" name="lastname" required>
            </div>

            <div class="form-group">
                <label for="dob">Date of Birth:</label>
                <input type="date" id="dob" name="dob">
            </div>

            <div class="form-group">
                <label>Gender:</label>
                <input type="radio" id="male" name="gender" value="male">
                <label for="male" style="display: inline;">Male</label>

                <input type="radio" id="female" name="gender" value="female">
                <label for="female" style="display: inline;">Female</label>

                <input type="radio" id="other" name="gender" value="other">
                <label for="other" style="display: inline;">Other</label>
            </div>
        </fieldset>

        <br>

        <!-- Contact Information -->
        <fieldset>
            <legend>Contact Information</legend>

            <div class="form-group">
                <label for="email">Email: *</label>
                <input type="email" id="email" name="email" required>
            </div>

            <div class="form-group">
                <label for="phone">Phone:</label>
                <input type="tel" id="phone" name="phone" pattern="[0-9]{10}">
            </div>

            <div class="form-group">
                <label for="address">Address:</label>
                <textarea id="address" name="address" rows="3"></textarea>
            </div>

            <div class="form-group">
                <label for="country">Country:</label>
                <select id="country" name="country">
                    <option value="">-- Select Country --</option>
                    <option value="nepal">Nepal</option>
                    <option value="india">India</option>
                    <option value="usa">USA</option>
                    <option value="uk">UK</option>
                </select>
            </div>
        </fieldset>

        <br>

        <!-- Account Information -->
        <fieldset>
            <legend>Account Information</legend>

            <div class="form-group">
                <label for="username">Username: *</label>
                <input type="text" id="username" name="username" required minlength="5">
            </div>

            <div class="form-group">
                <label for="password">Password: *</label>
                <input type="password" id="password" name="password" required minlength="8">
            </div>

            <div class="form-group">
                <label for="confirm-password">Confirm Password: *</label>
                <input type="password" id="confirm-password" name="confirm_password" required>
            </div>

            <div class="form-group">
                <label for="profile-pic">Profile Picture:</label>
                <input type="file" id="profile-pic" name="profile_pic" accept="image/*">
            </div>
        </fieldset>

        <br>

        <!-- Preferences -->
        <fieldset>
            <legend>Preferences</legend>

            <div class="form-group">
                <label>Interests (select multiple):</label>
                <input type="checkbox" id="sports" name="interests[]" value="sports">
                <label for="sports" style="display: inline;">Sports</label><br>

                <input type="checkbox" id="music" name="interests[]" value="music">
                <label for="music" style="display: inline;">Music</label><br>

                <input type="checkbox" id="tech" name="interests[]" value="technology">
                <label for="tech" style="display: inline;">Technology</label><br>

                <input type="checkbox" id="travel" name="interests[]" value="travel">
                <label for="travel" style="display: inline;">Travel</label>
            </div>

            <div class="form-group">
                <input type="checkbox" id="newsletter" name="newsletter" value="yes">
                <label for="newsletter" style="display: inline;">Subscribe to newsletter</label>
            </div>

            <div class="form-group">
                <input type="checkbox" id="terms" name="terms" value="accepted" required>
                <label for="terms" style="display: inline;">I agree to Terms and Conditions *</label>
            </div>
        </fieldset>

        <br>

        <!-- Hidden fields -->
        <input type="hidden" name="form_id" value="registration_v2">
        <input type="hidden" name="timestamp" value="<?php echo time(); ?>">

        <!-- Buttons -->
        <button type="submit" class="submit-btn">Register</button>
        <button type="reset">Clear Form</button>
    </form>

    <p><small>* Required fields</small></p>
</body>
</html>
```

---

### Summary

**Key Takeaways:**

✅ **`<form>`**: Container for form elements
✅ **`action`**: Where to send data
✅ **`method`**: GET (visible in URL) or POST (hidden, secure)
✅ **`<input type="text">`**: Single-line text
✅ **`<input type="password">`**: Hidden text
✅ **`<input type="email">`**: Email with validation
✅ **`<input type="checkbox">`**: Multiple selections
✅ **`<input type="radio">`**: Single selection from group
✅ **`<select>`**: Dropdown list
✅ **`<textarea>`**: Multi-line text
✅ **`<button>` or `<input type="submit">`**: Submit form
✅ **`id`**: Unique identifier
✅ **`class`**: Reusable style class
✅ **`<label>`**: Associates text with input (accessibility)

**Next Steps:**
Now you understand forms! Next, you'll learn about semantic HTML5 elements that give meaning to your page structure!
