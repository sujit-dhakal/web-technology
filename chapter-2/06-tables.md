# Chapter 2: Introduction to HTML - Part 6
## Tables

### 1. Introduction to HTML Tables

**What are Tables?**

Tables are used to display data in rows and columns - similar to spreadsheets. They organize information in a structured, grid-like format.

**Real-World Analogy:**

Think of an HTML table like a classroom seating chart or a train schedule—data organized in rows and columns for easy reading.

**When to Use Tables:**

✅ Spreadsheet-like data (prices, schedules, statistics)
✅ Comparison charts
✅ Data reports
❌ **Not for page layout** (use CSS Grid/Flexbox instead)

---

### 2. Basic Table Structure

**Essential Table Elements:**

- `<table>` - Container for the entire table
- `<tr>` - Table Row
- `<td>` - Table Data (cell)
- `<th>` - Table Header (bold, centered by default)

**Basic Syntax:**
```html
<table>
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Table</title>
</head>
<body>
    <h1>Student Information</h1>

    <table border="1">
        <tr>
            <th>Name</th>
            <th>Roll No</th>
            <th>Grade</th>
        </tr>
        <tr>
            <td>Ram Sharma</td>
            <td>101</td>
            <td>A</td>
        </tr>
        <tr>
            <td>Sita Rai</td>
            <td>102</td>
            <td>A+</td>
        </tr>
        <tr>
            <td>Hari Thapa</td>
            <td>103</td>
            <td>B+</td>
        </tr>
    </table>
</body>
</html>
```

**Visual Output:**
```
┌──────────────┬──────────┬────────┐
│ Name         │ Roll No  │ Grade  │ (header row)
├──────────────┼──────────┼────────┤
│ Ram Sharma   │ 101      │ A      │
│ Sita Rai     │ 102      │ A+     │
│ Hari Thapa   │ 103      │ B+     │
└──────────────┴──────────┴────────┘
```

---

### 3. Table Attributes

#### a) `border` Attribute

Adds border to table (deprecated in HTML5, use CSS instead):

```html
<table border="1">
```

#### b) `width` and `height`

```html
<table width="500" height="300">
<table width="80%">
```

#### c) `cellpadding` and `cellspacing`

```html
<!-- Space between cell border and content -->
<table border="1" cellpadding="10">

<!-- Space between cells -->
<table border="1" cellspacing="5">
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Table Attributes</title>
</head>
<body>
    <h2>Table with Cellpadding</h2>
    <table border="1" cellpadding="15">
        <tr>
            <th>Product</th>
            <th>Price</th>
        </tr>
        <tr>
            <td>Laptop</td>
            <td>Rs. 75,000</td>
        </tr>
        <tr>
            <td>Mouse</td>
            <td>Rs. 500</td>
        </tr>
    </table>

    <h2>Table with Cellspacing</h2>
    <table border="1" cellspacing="10">
        <tr>
            <th>Product</th>
            <th>Price</th>
        </tr>
        <tr>
            <td>Laptop</td>
            <td>Rs. 75,000</td>
        </tr>
        <tr>
            <td>Mouse</td>
            <td>Rs. 500</td>
        </tr>
    </table>
</body>
</html>
```

---

### 4. Table Sections: `<thead>`, `<tbody>`, `<tfoot>`

**Why Use Sections?**

- Better organization
- Semantic structure
- Easier styling
- Better accessibility

**Structure:**

```html
<table>
    <thead>
        <!-- Header rows -->
    </thead>
    <tbody>
        <!-- Main data rows -->
    </tbody>
    <tfoot>
        <!-- Footer rows (totals, summaries) -->
    </tfoot>
</table>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Table Sections</title>
    <style>
        table { border-collapse: collapse; width: 100%; }
        th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
        thead { background-color: #4CAF50; color: white; }
        tbody tr:nth-child(even) { background-color: #f2f2f2; }
        tfoot { background-color: #f9f9f9; font-weight: bold; }
    </style>
</head>
<body>
    <h1>Monthly Sales Report</h1>

    <table>
        <thead>
            <tr>
                <th>Product</th>
                <th>Units Sold</th>
                <th>Price</th>
                <th>Total</th>
            </tr>
        </thead>

        <tbody>
            <tr>
                <td>Laptop</td>
                <td>5</td>
                <td>Rs. 75,000</td>
                <td>Rs. 375,000</td>
            </tr>
            <tr>
                <td>Mouse</td>
                <td>20</td>
                <td>Rs. 500</td>
                <td>Rs. 10,000</td>
            </tr>
            <tr>
                <td>Keyboard</td>
                <td>15</td>
                <td>Rs. 1,500</td>
                <td>Rs. 22,500</td>
            </tr>
        </tbody>

        <tfoot>
            <tr>
                <td colspan="3">Grand Total</td>
                <td>Rs. 407,500</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

---

### 5. Colspan (Merging Columns)

**What is Colspan?**

Merges multiple columns into one cell horizontally.

**Syntax:**
```html
<td colspan="number">Content</td>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Colspan Example</title>
    <style>
        table { border-collapse: collapse; width: 100%; }
        th, td { border: 1px solid black; padding: 10px; text-align: center; }
    </style>
</head>
<body>
    <h1>Class Schedule</h1>

    <table>
        <tr>
            <th>Time</th>
            <th>Monday</th>
            <th>Tuesday</th>
            <th>Wednesday</th>
        </tr>
        <tr>
            <td>9:00 AM</td>
            <td>Math</td>
            <td>English</td>
            <td>Science</td>
        </tr>
        <tr>
            <td>10:00 AM</td>
            <td colspan="3">Assembly (All Classes)</td>
        </tr>
        <tr>
            <td>11:00 AM</td>
            <td>History</td>
            <td colspan="2">Computer Lab</td>
        </tr>
    </table>
</body>
</html>
```

**Visual Representation:**
```
┌──────────┬─────────┬──────────┬───────────┐
│ Time     │ Monday  │ Tuesday  │ Wednesday │
├──────────┼─────────┼──────────┼───────────┤
│ 9:00 AM  │ Math    │ English  │ Science   │
├──────────┼─────────┴──────────┴───────────┤
│ 10:00 AM │ Assembly (All Classes)         │
├──────────┼─────────┬──────────────────────┤
│ 11:00 AM │ History │ Computer Lab         │
└──────────┴─────────┴──────────────────────┘
```

---

### 6. Rowspan (Merging Rows)

**What is Rowspan?**

Merges multiple rows into one cell vertically.

**Syntax:**
```html
<td rowspan="number">Content</td>
```

**Example:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Rowspan Example</title>
    <style>
        table { border-collapse: collapse; width: 100%; }
        th, td { border: 1px solid black; padding: 10px; text-align: center; }
    </style>
</head>
<body>
    <h1>Weekly Timetable</h1>

    <table>
        <tr>
            <th>Day</th>
            <th>Morning</th>
            <th>Afternoon</th>
        </tr>
        <tr>
            <td>Monday</td>
            <td>Math</td>
            <td>Science</td>
        </tr>
        <tr>
            <td>Tuesday</td>
            <td rowspan="2">Computer Lab</td>
            <td>English</td>
        </tr>
        <tr>
            <td>Wednesday</td>
            <!-- Computer Lab continues here -->
            <td>History</td>
        </tr>
        <tr>
            <td>Thursday</td>
            <td>Physics</td>
            <td rowspan="2">Sports</td>
        </tr>
        <tr>
            <td>Friday</td>
            <td>Chemistry</td>
            <!-- Sports continues here -->
        </tr>
    </table>
</body>
</html>
```

**Visual Representation:**
```
┌───────────┬──────────────┬───────────┐
│ Day       │ Morning      │ Afternoon │
├───────────┼──────────────┼───────────┤
│ Monday    │ Math         │ Science   │
├───────────┼──────────────┼───────────┤
│ Tuesday   │ Computer Lab │ English   │
├───────────┤              ├───────────┤
│ Wednesday │              │ History   │
├───────────┼──────────────┼───────────┤
│ Thursday  │ Physics      │ Sports    │
├───────────┼──────────────┤           │
│ Friday    │ Chemistry    │           │
└───────────┴──────────────┴───────────┘
```

---

### 7. Combining Colspan and Rowspan

```html
<!DOCTYPE html>
<html>
<head>
    <title>Complex Table</title>
    <style>
        table { border-collapse: collapse; width: 600px; }
        th, td { border: 2px solid #333; padding: 10px; text-align: center; }
        th { background-color: #4CAF50; color: white; }
    </style>
</head>
<body>
    <h1>Exam Schedule</h1>

    <table>
        <tr>
            <th rowspan="2">Date</th>
            <th colspan="2">Morning Session</th>
            <th colspan="2">Afternoon Session</th>
        </tr>
        <tr>
            <th>Subject</th>
            <th>Time</th>
            <th>Subject</th>
            <th>Time</th>
        </tr>
        <tr>
            <td>Jan 15</td>
            <td>Mathematics</td>
            <td>9:00 AM</td>
            <td>Physics</td>
            <td>2:00 PM</td>
        </tr>
        <tr>
            <td>Jan 16</td>
            <td colspan="2">English (3 hours) - 9:00 AM</td>
            <td>Chemistry</td>
            <td>2:00 PM</td>
        </tr>
        <tr>
            <td>Jan 17</td>
            <td>Computer</td>
            <td>9:00 AM</td>
            <td colspan="2" rowspan="2">Practical Exam<br>Multi-Session</td>
        </tr>
        <tr>
            <td>Jan 18</td>
            <td>Biology</td>
            <td>9:00 AM</td>
        </tr>
    </table>
</body>
</html>
```

---

### 8. Styling Tables with CSS

**Modern Table Styling:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Styled Table</title>
    <style>
        table {
            border-collapse: collapse;
            width: 100%;
            margin: 20px 0;
            font-family: Arial, sans-serif;
        }

        th {
            background-color: #3498db;
            color: white;
            padding: 12px;
            text-align: left;
        }

        td {
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }

        /* Zebra striping */
        tbody tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        /* Hover effect */
        tbody tr:hover {
            background-color: #e8f4f8;
        }

        /* Responsive table */
        @media screen and (max-width: 600px) {
            table {
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <h1>Product Catalog</h1>

    <table>
        <thead>
            <tr>
                <th>Product ID</th>
                <th>Product Name</th>
                <th>Category</th>
                <th>Price</th>
                <th>Stock</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>P001</td>
                <td>Laptop HP</td>
                <td>Electronics</td>
                <td>Rs. 75,000</td>
                <td>15</td>
            </tr>
            <tr>
                <td>P002</td>
                <td>Wireless Mouse</td>
                <td>Accessories</td>
                <td>Rs. 800</td>
                <td>50</td>
            </tr>
            <tr>
                <td>P003</td>
                <td>USB Cable</td>
                <td>Accessories</td>
                <td>Rs. 150</td>
                <td>100</td>
            </tr>
            <tr>
                <td>P004</td>
                <td>Monitor Dell 24"</td>
                <td>Electronics</td>
                <td>Rs. 25,000</td>
                <td>8</td>
            </tr>
            <tr>
                <td>P005</td>
                <td>Keyboard Mechanical</td>
                <td>Accessories</td>
                <td>Rs. 3,500</td>
                <td>20</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

---

### 9. Practical Examples

#### Example 1: Price Comparison Table

```html
<!DOCTYPE html>
<html>
<head>
    <title>Price Comparison</title>
    <style>
        table { border-collapse: collapse; width: 100%; }
        th, td { border: 1px solid #ddd; padding: 12px; text-align: center; }
        th { background-color: #2c3e50; color: white; }
        .best-price { background-color: #2ecc71; color: white; font-weight: bold; }
    </style>
</head>
<body>
    <h1>Laptop Price Comparison</h1>

    <table>
        <thead>
            <tr>
                <th>Model</th>
                <th>Processor</th>
                <th>RAM</th>
                <th>Storage</th>
                <th>Price</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>HP Pavilion</td>
                <td>Intel i5</td>
                <td>8 GB</td>
                <td>512 GB SSD</td>
                <td class="best-price">Rs. 75,000</td>
            </tr>
            <tr>
                <td>Dell Inspiron</td>
                <td>Intel i5</td>
                <td>8 GB</td>
                <td>1 TB HDD</td>
                <td>Rs. 80,000</td>
            </tr>
            <tr>
                <td>Lenovo ThinkPad</td>
                <td>Intel i7</td>
                <td>16 GB</td>
                <td>512 GB SSD</td>
                <td>Rs. 95,000</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

#### Example 2: Restaurant Menu

```html
<!DOCTYPE html>
<html>
<head>
    <title>Restaurant Menu</title>
    <style>
        body { font-family: 'Georgia', serif; background-color: #f9f9f9; padding: 20px; }
        table { border-collapse: collapse; width: 100%; background: white; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        th { background-color: #8B4513; color: white; padding: 15px; font-size: 18px; }
        td { padding: 12px; border-bottom: 1px solid #eee; }
        .item-name { font-weight: bold; color: #333; }
        .price { color: #2ecc71; font-weight: bold; text-align: right; }
        .category { background-color: #f0e68c; font-weight: bold; text-align: center; }
    </style>
</head>
<body>
    <h1 style="text-align: center; color: #8B4513;">Himalayan Restaurant Menu</h1>

    <table>
        <tr class="category">
            <td colspan="2">APPETIZERS</td>
        </tr>
        <tr>
            <td class="item-name">Chicken Momo (8 pcs)</td>
            <td class="price">Rs. 150</td>
        </tr>
        <tr>
            <td class="item-name">Vegetable Samosa (2 pcs)</td>
            <td class="price">Rs. 60</td>
        </tr>

        <tr class="category">
            <td colspan="2">MAIN COURSE</td>
        </tr>
        <tr>
            <td class="item-name">Dal Bhat Set</td>
            <td class="price">Rs. 250</td>
        </tr>
        <tr>
            <td class="item-name">Chicken Curry</td>
            <td class="price">Rs. 300</td>
        </tr>
        <tr>
            <td class="item-name">Vegetable Thukpa</td>
            <td class="price">Rs. 180</td>
        </tr>

        <tr class="category">
            <td colspan="2">BEVERAGES</td>
        </tr>
        <tr>
            <td class="item-name">Masala Tea</td>
            <td class="price">Rs. 40</td>
        </tr>
        <tr>
            <td class="item-name">Lassi</td>
            <td class="price">Rs. 80</td>
        </tr>
    </table>
</body>
</html>
```

---

### 10. Accessibility Best Practices

**Caption Element:**

```html
<table>
    <caption>Student Grades - Fall 2025</caption>
    <tr>
        <th>Name</th>
        <th>Grade</th>
    </tr>
    <!-- ... -->
</table>
```

**`scope` Attribute for Headers:**

```html
<table>
    <tr>
        <th scope="col">Name</th>
        <th scope="col">Age</th>
    </tr>
    <tr>
        <th scope="row">Ram</th>
        <td>25</td>
    </tr>
</table>
```

---

### Summary

**Key Takeaways:**

✅ **`<table>`**: Container for table
✅ **`<tr>`**: Table row
✅ **`<td>`**: Table data cell
✅ **`<th>`**: Table header cell (bold, centered)
✅ **`<thead>`, `<tbody>`, `<tfoot>`**: Table sections
✅ **`colspan`**: Merge columns horizontally
✅ **`rowspan`**: Merge rows vertically
✅ **`border`**: Add table borders (use CSS instead)
✅ **Use tables for data, not layout**
✅ **Use CSS for modern styling**

**Quick Reference:**

```html
<table border="1">
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
        </tr>
        <tr>
            <td colspan="2">Merged columns</td>
        </tr>
    </tbody>
</table>
```

**Next Steps:**
Now you understand tables! Next, you'll learn about frames (and why they're deprecated) and their modern alternatives.
