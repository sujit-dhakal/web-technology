# Chapter 2: Introduction to HTML - Part 11
## HTML Events

### 1. Introduction to HTML Events

**What are HTML Events?**

Events are actions or occurrences that happen in the browser that JavaScript can respond to. Events make web pages **interactive** - they respond to user actions!

**Real-World Analogy:**

Think of events like a doorbell:
- **Event**: Someone presses the doorbell button (user clicks a button)
- **Event handler**: The bell rings (JavaScript function executes)
- **Response**: You open the door (page shows a message or changes something)

**Common Events:**

- Mouse clicks
- Page loading
- Keyboard presses
- Form submissions
- Mouse hovering
- Window resizing

---

### 2. How Events Work

**Event Syntax:**

```html
<element event="JavaScript code">
```

**Example:**

```html
<button onclick="alert('Button clicked!')">Click Me</button>
```

**When button is clicked → JavaScript code runs → Alert appears**

---

### 3. Window Events

Window events occur on the browser window itself.

#### a) `onload`

Executes when page finishes loading.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Onload Event</title>
</head>
<body onload="alert('Welcome! Page has loaded.')">
    <h1>Welcome to My Website</h1>
    <p>The page has finished loading.</p>
</body>
</html>
```

**Better way (external JavaScript):**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Onload Event</title>
    <script>
        window.onload = function() {
            document.getElementById('message').innerHTML = 'Page loaded at: ' + new Date();
        };
    </script>
</head>
<body>
    <h1>Welcome!</h1>
    <p id="message"></p>
</body>
</html>
```

#### b) `onresize`

Executes when browser window is resized.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Onresize Event</title>
</head>
<body onresize="showSize()">
    <h1>Resize your browser window</h1>
    <p id="size"></p>

    <script>
        function showSize() {
            const width = window.innerWidth;
            const height = window.innerHeight;
            document.getElementById('size').innerHTML =
                `Window size: ${width} x ${height} pixels`;
        }

        // Show initial size
        showSize();
    </script>
</body>
</html>
```

#### c) `onscroll`

Executes when user scrolls the page.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Onscroll Event</title>
    <style>
        #scrollInfo {
            position: fixed;
            top: 0;
            background-color: #333;
            color: white;
            padding: 10px;
            width: 100%;
        }
        .content {
            margin-top: 60px;
            height: 2000px;
        }
    </style>
</head>
<body onscroll="trackScroll()">
    <div id="scrollInfo">Scroll position: 0px</div>

    <div class="content">
        <h1>Scroll down this page</h1>
        <p>Keep scrolling to see the scroll position update...</p>
    </div>

    <script>
        function trackScroll() {
            const scrollPos = window.pageYOffset;
            document.getElementById('scrollInfo').innerHTML =
                'Scroll position: ' + scrollPos + 'px';
        }
    </script>
</body>
</html>
```

#### d) `onunload` / `onbeforeunload`

Executes when user leaves the page.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Before Unload Event</title>
</head>
<body onbeforeunload="return 'Are you sure you want to leave?'">
    <h1>Try to close or refresh this tab</h1>
    <p>You'll get a confirmation message.</p>
</body>
</html>
```

---

### 4. Mouse Events

Events triggered by mouse actions.

#### a) `onclick`

Executes when element is clicked.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Click Event</title>
    <style>
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
        }
    </style>
</head>
<body>
    <h1>Click Counter</h1>

    <p>Button clicked <span id="count">0</span> times</p>

    <button onclick="incrementCounter()">Click Me!</button>
    <button onclick="resetCounter()">Reset</button>

    <script>
        let count = 0;

        function incrementCounter() {
            count++;
            document.getElementById('count').innerHTML = count;
        }

        function resetCounter() {
            count = 0;
            document.getElementById('count').innerHTML = count;
        }
    </script>
</body>
</html>
```

#### b) `ondblclick`

Executes on double-click.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Double Click Event</title>
    <style>
        .box {
            width: 200px;
            height: 200px;
            background-color: lightblue;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            margin: 20px;
        }
    </style>
</head>
<body>
    <h1>Double-click the box to change color</h1>

    <div class="box" id="colorBox" ondblclick="changeColor()">
        Double-click me!
    </div>

    <script>
        function changeColor() {
            const colors = ['lightblue', 'lightgreen', 'lightcoral', 'lightyellow', 'lightpink'];
            const randomColor = colors[Math.floor(Math.random() * colors.length)];
            document.getElementById('colorBox').style.backgroundColor = randomColor;
        }
    </script>
</body>
</html>
```

#### c) `onmouseover` and `onmouseout`

Execute when mouse enters/leaves element.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Mouse Hover Events</title>
    <style>
        .card {
            width: 250px;
            padding: 20px;
            margin: 20px;
            background-color: #f0f0f0;
            border: 2px solid transparent;
            transition: all 0.3s;
        }
    </style>
</head>
<body>
    <h1>Hover over the cards</h1>

    <div class="card"
         id="card1"
         onmouseover="hoverIn(this)"
         onmouseout="hoverOut(this)">
        <h3>Card 1</h3>
        <p>Hover to see effect</p>
    </div>

    <div class="card"
         id="card2"
         onmouseover="hoverIn(this)"
         onmouseout="hoverOut(this)">
        <h3>Card 2</h3>
        <p>Hover to see effect</p>
    </div>

    <script>
        function hoverIn(element) {
            element.style.backgroundColor = '#4CAF50';
            element.style.color = 'white';
            element.style.borderColor = '#333';
            element.style.transform = 'scale(1.05)';
        }

        function hoverOut(element) {
            element.style.backgroundColor = '#f0f0f0';
            element.style.color = 'black';
            element.style.borderColor = 'transparent';
            element.style.transform = 'scale(1)';
        }
    </script>
</body>
</html>
```

#### d) `onmousemove`

Executes when mouse moves over element.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Mouse Move Event</title>
    <style>
        #tracker {
            width: 600px;
            height: 400px;
            border: 2px solid black;
            position: relative;
            background-color: #f9f9f9;
        }
        #dot {
            width: 20px;
            height: 20px;
            background-color: red;
            border-radius: 50%;
            position: absolute;
        }
    </style>
</head>
<body>
    <h1>Mouse Tracker</h1>
    <p id="coordinates">X: 0, Y: 0</p>

    <div id="tracker" onmousemove="trackMouse(event)">
        <div id="dot"></div>
    </div>

    <script>
        function trackMouse(e) {
            const tracker = document.getElementById('tracker');
            const dot = document.getElementById('dot');
            const coords = document.getElementById('coordinates');

            const rect = tracker.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;

            dot.style.left = (x - 10) + 'px';
            dot.style.top = (y - 10) + 'px';

            coords.innerHTML = `X: ${Math.round(x)}, Y: ${Math.round(y)}`;
        }
    </script>
</body>
</html>
```

#### e) `oncontextmenu`

Executes on right-click (context menu).

```html
<!DOCTYPE html>
<html>
<head>
    <title>Context Menu Event</title>
</head>
<body>
    <h1>Right-click Prevention</h1>

    <div oncontextmenu="return false;" style="padding: 20px; background: #f0f0f0;">
        <p>Try right-clicking inside this box - it's disabled!</p>
    </div>

    <br>

    <div oncontextmenu="showCustomMenu(); return false;" style="padding: 20px; background: #e0e0e0;">
        <p>Right-click here for custom message</p>
    </div>

    <script>
        function showCustomMenu() {
            alert('Custom context menu could appear here!');
        }
    </script>
</body>
</html>
```

---

### 5. Keyboard Events

Events triggered by keyboard actions.

#### a) `onkeydown`

Executes when key is pressed down.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Keydown Event</title>
</head>
<body>
    <h1>Keyboard Event Demo</h1>

    <p>Press any key on your keyboard:</p>
    <div id="keyInfo" style="padding: 20px; background: #f0f0f0; font-size: 20px;">
        Waiting for key press...
    </div>

    <script>
        document.onkeydown = function(event) {
            const keyInfo = document.getElementById('keyInfo');
            keyInfo.innerHTML = `
                Key: ${event.key}<br>
                Key Code: ${event.keyCode}<br>
                Code: ${event.code}
            `;
        };
    </script>
</body>
</html>
```

#### b) `onkeyup`

Executes when key is released.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Keyup Event</title>
</head>
<body>
    <h1>Character Counter</h1>

    <textarea id="textInput"
              rows="5"
              cols="50"
              placeholder="Start typing..."
              onkeyup="countCharacters()"></textarea>

    <p>Characters: <span id="charCount">0</span></p>
    <p>Words: <span id="wordCount">0</span></p>

    <script>
        function countCharacters() {
            const text = document.getElementById('textInput').value;
            const chars = text.length;
            const words = text.trim().split(/\s+/).filter(word => word.length > 0).length;

            document.getElementById('charCount').innerHTML = chars;
            document.getElementById('wordCount').innerHTML = words;
        }
    </script>
</body>
</html>
```

#### c) `onkeypress`

Executes when key is pressed (being deprecated, use keydown instead).

```html
<!DOCTYPE html>
<html>
<head>
    <title>Keypress Event</title>
</head>
<body>
    <h1>Type to Build Text</h1>

    <input type="text"
           id="typeBox"
           onkeypress="displayKey(event)"
           placeholder="Type something...">

    <p id="output"></p>

    <script>
        function displayKey(event) {
            const output = document.getElementById('output');
            output.innerHTML += event.key;
        }
    </script>
</body>
</html>
```

#### d) Special Key Detection

```html
<!DOCTYPE html>
<html>
<head>
    <title>Special Keys</title>
    <style>
        .box {
            width: 200px;
            height: 200px;
            background-color: lightblue;
            position: relative;
            top: 100px;
            left: 100px;
        }
    </style>
</head>
<body onkeydown="moveBox(event)">
    <h1>Move the Box with Arrow Keys</h1>
    <p>Use ↑ ↓ ← → arrow keys</p>

    <div id="movingBox" class="box"></div>

    <script>
        let top = 100;
        let left = 100;

        function moveBox(e) {
            const box = document.getElementById('movingBox');
            const step = 10;

            switch(e.key) {
                case 'ArrowUp':
                    top -= step;
                    e.preventDefault();
                    break;
                case 'ArrowDown':
                    top += step;
                    e.preventDefault();
                    break;
                case 'ArrowLeft':
                    left -= step;
                    e.preventDefault();
                    break;
                case 'ArrowRight':
                    left += step;
                    e.preventDefault();
                    break;
            }

            box.style.top = top + 'px';
            box.style.left = left + 'px';
        }
    </script>
</body>
</html>
```

---

### 6. Form Element Events

Events specific to form elements.

#### a) `onsubmit`

Executes when form is submitted.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Submit Event</title>
</head>
<body>
    <h1>Registration Form</h1>

    <form onsubmit="return validateForm()" action="#" method="POST">
        <label for="username">Username:</label><br>
        <input type="text" id="username" name="username" required><br><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" required><br><br>

        <label for="password">Password:</label><br>
        <input type="password" id="password" name="password" required><br><br>

        <button type="submit">Register</button>
    </form>

    <script>
        function validateForm() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            if (username.length < 5) {
                alert('Username must be at least 5 characters!');
                return false; // Prevent form submission
            }

            if (password.length < 8) {
                alert('Password must be at least 8 characters!');
                return false;
            }

            alert('Form submitted successfully!');
            return true; // Allow form submission
        }
    </script>
</body>
</html>
```

#### b) `onchange`

Executes when element value changes.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Event</title>
</head>
<body>
    <h1>Product Selection</h1>

    <label for="product">Select Product:</label>
    <select id="product" onchange="updatePrice()">
        <option value="">-- Select --</option>
        <option value="laptop">Laptop - Rs. 75,000</option>
        <option value="mouse">Mouse - Rs. 800</option>
        <option value="keyboard">Keyboard - Rs. 2,500</option>
    </select>

    <p id="priceDisplay"></p>

    <script>
        function updatePrice() {
            const product = document.getElementById('product').value;
            const display = document.getElementById('priceDisplay');

            const prices = {
                laptop: 'Rs. 75,000',
                mouse: 'Rs. 800',
                keyboard: 'Rs. 2,500'
            };

            if (product) {
                display.innerHTML = `Price: ${prices[product]}`;
            } else {
                display.innerHTML = '';
            }
        }
    </script>
</body>
</html>
```

#### c) `onfocus` and `onblur`

Execute when element gains/loses focus.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Focus Events</title>
    <style>
        input {
            padding: 10px;
            margin: 10px 0;
            border: 2px solid #ddd;
        }
        .focused {
            border-color: #4CAF50;
            background-color: #f0fff0;
        }
    </style>
</head>
<body>
    <h1>Form with Focus Events</h1>

    <form>
        <label for="name">Name:</label><br>
        <input type="text"
               id="name"
               onfocus="highlightField(this)"
               onblur="normalizeField(this)"
               placeholder="Enter your name"><br>

        <label for="email">Email:</label><br>
        <input type="email"
               id="email"
               onfocus="highlightField(this)"
               onblur="normalizeField(this)"
               placeholder="Enter your email"><br>

        <label for="phone">Phone:</label><br>
        <input type="tel"
               id="phone"
               onfocus="highlightField(this)"
               onblur="normalizeField(this)"
               placeholder="Enter your phone"><br>
    </form>

    <script>
        function highlightField(element) {
            element.classList.add('focused');
        }

        function normalizeField(element) {
            element.classList.remove('focused');
        }
    </script>
</body>
</html>
```

#### d) `oninput`

Executes immediately when input value changes (real-time).

```html
<!DOCTYPE html>
<html>
<head>
    <title>Input Event</title>
    <style>
        .live-preview {
            padding: 20px;
            background-color: #f0f0f0;
            margin-top: 20px;
            min-height: 50px;
        }
    </style>
</head>
<body>
    <h1>Live Preview</h1>

    <label for="heading">Enter Heading:</label><br>
    <input type="text"
           id="heading"
           oninput="updatePreview()"
           placeholder="Type heading..."
           style="width: 300px; padding: 10px;">
    <br><br>

    <label for="content">Enter Content:</label><br>
    <textarea id="content"
              rows="5"
              cols="50"
              oninput="updatePreview()"
              placeholder="Type content..."></textarea>

    <div class="live-preview">
        <h2 id="previewHeading">Heading Preview</h2>
        <p id="previewContent">Content preview will appear here...</p>
    </div>

    <script>
        function updatePreview() {
            const heading = document.getElementById('heading').value;
            const content = document.getElementById('content').value;

            document.getElementById('previewHeading').innerHTML =
                heading || 'Heading Preview';
            document.getElementById('previewContent').innerHTML =
                content || 'Content preview will appear here...';
        }
    </script>
</body>
</html>
```

---

### 7. Complete Interactive Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Event Demo</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        h1 { color: #333; margin-bottom: 20px; }

        .section {
            margin: 20px 0;
            padding: 20px;
            background: #f9f9f9;
            border-radius: 5px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }

        button:hover {
            background-color: #45a049;
        }

        input, textarea {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 2px solid #ddd;
            border-radius: 5px;
        }

        .color-box {
            width: 100%;
            height: 100px;
            background-color: lightblue;
            border-radius: 5px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }
    </style>
</head>
<body onload="init()">
    <div class="container">
        <h1>🎯 Interactive Events Playground</h1>

        <!-- Click Counter -->
        <div class="section">
            <h2>1. Click Events</h2>
            <p>Clicks: <span id="clicks">0</span></p>
            <button onclick="incrementClicks()">Click Me!</button>
            <button onclick="resetClicks()">Reset</button>
        </div>

        <!-- Hover Effect -->
        <div class="section">
            <h2>2. Mouse Hover Events</h2>
            <div class="color-box"
                 id="hoverBox"
                 onmouseover="boxHoverIn()"
                 onmouseout="boxHoverOut()">
                Hover over me!
            </div>
        </div>

        <!-- Keyboard Events -->
        <div class="section">
            <h2>3. Keyboard Events</h2>
            <input type="text"
                   id="keyInput"
                   placeholder="Type something..."
                   onkeyup="showKeyInfo(event)">
            <p id="keyDisplay">Last key: -</p>
        </div>

        <!-- Form Events -->
        <div class="section">
            <h2>4. Form Events</h2>
            <form onsubmit="handleSubmit(event)">
                <input type="text"
                       id="nameInput"
                       placeholder="Your name"
                       onfocus="showHint('nameHint')"
                       onblur="hideHint('nameHint')"
                       oninput="validateName()">
                <p id="nameHint" style="color: #666; display: none;">
                    📝 Enter at least 3 characters
                </p>
                <p id="nameValidation"></p>
                <button type="submit">Submit</button>
            </form>
        </div>

        <!-- Window Info -->
        <div class="section">
            <h2>5. Window Events</h2>
            <p id="windowInfo">Window size: -</p>
            <button onclick="updateWindowInfo()">Update Info</button>
        </div>
    </div>

    <script>
        let clickCount = 0;

        // Initialize
        function init() {
            updateWindowInfo();
            console.log('Page loaded successfully!');
        }

        // Click events
        function incrementClicks() {
            clickCount++;
            document.getElementById('clicks').innerHTML = clickCount;
        }

        function resetClicks() {
            clickCount = 0;
            document.getElementById('clicks').innerHTML = clickCount;
        }

        // Hover events
        function boxHoverIn() {
            const box = document.getElementById('hoverBox');
            box.style.backgroundColor = '#4CAF50';
            box.style.color = 'white';
            box.style.transform = 'scale(1.05)';
            box.innerHTML = 'Nice! 😊';
        }

        function boxHoverOut() {
            const box = document.getElementById('hoverBox');
            box.style.backgroundColor = 'lightblue';
            box.style.color = 'black';
            box.style.transform = 'scale(1)';
            box.innerHTML = 'Hover over me!';
        }

        // Keyboard events
        function showKeyInfo(event) {
            const display = document.getElementById('keyDisplay');
            display.innerHTML = `Last key: <strong>${event.key}</strong> (Code: ${event.code})`;
        }

        // Form events
        function showHint(id) {
            document.getElementById(id).style.display = 'block';
        }

        function hideHint(id) {
            document.getElementById(id).style.display = 'none';
        }

        function validateName() {
            const name = document.getElementById('nameInput').value;
            const validation = document.getElementById('nameValidation');

            if (name.length >= 3) {
                validation.innerHTML = '✅ Valid name';
                validation.style.color = 'green';
            } else if (name.length > 0) {
                validation.innerHTML = '⚠️ Too short';
                validation.style.color = 'orange';
            } else {
                validation.innerHTML = '';
            }
        }

        function handleSubmit(event) {
            event.preventDefault();
            const name = document.getElementById('nameInput').value;

            if (name.length >= 3) {
                alert(`Hello, ${name}! Form submitted successfully!`);
            } else {
                alert('Please enter a valid name (at least 3 characters)');
            }
        }

        // Window events
        function updateWindowInfo() {
            const info = document.getElementById('windowInfo');
            info.innerHTML = `Window size: ${window.innerWidth} x ${window.innerHeight} pixels`;
        }

        // Update on window resize
        window.onresize = updateWindowInfo;
    </script>
</body>
</html>
```

---

### 8. Event Types Summary

| Event Category | Events | When Triggered |
|----------------|--------|----------------|
| **Window** | `onload`, `onresize`, `onscroll`, `onunload` | Page/window actions |
| **Mouse** | `onclick`, `ondblclick`, `onmouseover`, `onmouseout`, `onmousemove` | Mouse interactions |
| **Keyboard** | `onkeydown`, `onkeyup`, `onkeypress` | Keyboard actions |
| **Form** | `onsubmit`, `onchange`, `onfocus`, `onblur`, `oninput` | Form interactions |

---

### Summary

**Key Takeaways:**

✅ **Events**: Actions that happen in the browser
✅ **Event handlers**: JavaScript code that responds to events
✅ **Window events**: `onload`, `onresize`, `onscroll`
✅ **Mouse events**: `onclick`, `onmouseover`, `ondblclick`
✅ **Keyboard events**: `onkeydown`, `onkeyup`
✅ **Form events**: `onsubmit`, `onchange`, `onfocus`, `oninput`
✅ **Syntax**: `<element event="JavaScript">`
✅ **Better practice**: Use external JavaScript functions

**Quick Reference:**

```html
<!-- Window Events -->
<body onload="init()">
<body onresize="handleResize()">

<!-- Mouse Events -->
<button onclick="handleClick()">Click</button>
<div onmouseover="handleHover()">Hover</div>

<!-- Keyboard Events -->
<input onkeyup="handleKey(event)">

<!-- Form Events -->
<form onsubmit="return validate()">
<input onfocus="showHint()" onblur="hideHint()">
<input oninput="liveUpdate()">
```

**Congratulations! 🎉**
You've completed all HTML topics in Chapter 2! You now have a solid foundation in HTML and are ready to build amazing web pages!

**Next Steps:**
- Practice building complete web pages
- Learn CSS for styling
- Learn JavaScript for advanced interactivity
- Build real projects!
