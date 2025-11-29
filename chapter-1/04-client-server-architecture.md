# Chapter 1: Web Basics - Part 4
## Client-Server Architecture

Client-Server architecture is a computing model where tasks are distributed between service providers (servers) and service requesters (clients). Let's explore different types of this architecture.

### 1. Single-Tier Architecture (1-Tier)

**What is Single-Tier Architecture?**

In single-tier architecture, all components of an application—presentation layer, business logic, and data storage—reside on a single machine. Everything runs locally on one computer.

**Structure:**
```
┌─────────────────────────────────────┐
│      USER'S COMPUTER                │
│  ┌────────────────────────────────┐ │
│  │  User Interface                │ │
│  ├────────────────────────────────┤ │
│  │  Business Logic                │ │
│  ├────────────────────────────────┤ │
│  │  Database                      │ │
│  └────────────────────────────────┘ │
└─────────────────────────────────────┘
```

**Real-World Analogy:**
Imagine a personal diary app on your computer that stores everything locally. You write entries, the app processes them, and saves them to your computer's hard drive—all on one machine.

**Examples:**
- Microsoft Word (processes and saves documents locally)
- Notepad
- Local media players (VLC)
- Simple calculator apps
- Offline games

**Characteristics:**
- All processing happens on one machine
- No network required
- Data stored locally
- No separation of concerns

**Example Scenario:**
You create a spreadsheet in Excel:
1. You enter data (presentation)
2. Excel calculates formulas (business logic)
3. Excel saves the file (data storage)
4. Everything happens on your computer

**Advantages:**
- ✅ No network dependency
- ✅ Fast (no network latency)
- ✅ Simple to develop
- ✅ Easy to deploy
- ✅ Works offline
- ✅ Low cost

**Disadvantages:**
- ❌ No data sharing between users
- ❌ Difficult to maintain/update
- ❌ No centralized control
- ❌ Multiple copies of data
- ❌ Not scalable
- ❌ Security risks if computer is compromised

### 2. Two-Tier Architecture (Client-Server)

**What is Two-Tier Architecture?**

Two-tier architecture splits the application into two parts: client (presentation layer) and server (database layer). The client handles the user interface and some business logic, while the server manages the database.

**Structure:**
```
┌─────────────────┐                ┌─────────────────┐
│   TIER 1        │                │   TIER 2        │
│   CLIENT        │                │   SERVER        │
│                 │  Request       │                 │
│  ┌───────────┐  │ ───────────>   │  ┌───────────┐  │
│  │  UI       │  │                │  │ Database  │  │
│  │  +        │  │                │  │           │  │
│  │  Logic    │  │  Response      │  │           │  │
│  └───────────┘  │ <─────────────  │  └───────────┘  │
└─────────────────┘                └─────────────────┘
  (User's Device)                     (Server Computer)
```

**Real-World Analogy:**
Think of an ATM machine. You (client) interact with the ATM interface, but your account data is stored on the bank's central server. The ATM connects to the server to check balance and process transactions.

**Examples:**
- Desktop email clients (Outlook connecting to email server)
- Railway/airline reservation systems
- Desktop banking applications
- Point of Sale (POS) systems in shops
- Online exam systems

**Detailed Example - Library Management System:**

**Client Side (Librarian's Computer):**
```
┌──────────────────────────────┐
│   Library Management App     │
│  ┌────────────────────────┐  │
│  │  Search Books          │  │
│  │  Issue Books           │  │
│  │  Return Books          │  │
│  │  Add Members           │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
         ↓ SQL Queries ↓
```

**Server Side (Central Database Server):**
```
┌──────────────────────────────┐
│   Database Server (MySQL)    │
│  ┌────────────────────────┐  │
│  │  Books Table           │  │
│  │  Members Table         │  │
│  │  Transactions Table    │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
```

**How It Works:**
1. Librarian enters student ID in app
2. App sends SQL query to database server
3. Server searches database for student records
4. Server sends back student information
5. App displays student details
6. Librarian issues book
7. App sends update query to server
8. Server updates database

**Advantages:**
- ✅ Centralized data management
- ✅ Multiple clients can access same data
- ✅ Better security (data on secure server)
- ✅ Easy to maintain database
- ✅ Reduced data redundancy
- ✅ Better performance than single-tier

**Disadvantages:**
- ❌ Client has business logic (harder to update)
- ❌ Network dependent
- ❌ Limited scalability
- ❌ Client needs to be powerful
- ❌ Direct database access (security risk)
- ❌ Difficult to change database

### 3. Three-Tier Architecture (Multi-Tier)

**What is Three-Tier Architecture?**

Three-tier architecture separates applications into three logical layers: presentation (client), application/business logic (middle tier), and data (database). This is the most common architecture for modern web applications.

**Structure:**
```
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│   TIER 1    │      │   TIER 2     │      │   TIER 3    │
│ Presentation│      │   Business   │      │   Data      │
│   Layer     │      │    Logic     │      │   Layer     │
│             │      │    Layer     │      │             │
│  ┌───────┐  │ HTTP │  ┌────────┐  │ SQL  │  ┌───────┐  │
│  │Browser│  │ ---> │  │App     │  │ ---> │  │Database│ │
│  │       │  │      │  │Server  │  │      │  │       │  │
│  │  UI   │  │      │  │(PHP/   │  │      │  │(MySQL)│  │
│  └───────┘  │ <--- │  │Java)   │  │ <--- │  └───────┘  │
│             │      │  └────────┘  │      │             │
└─────────────┘      └──────────────┘      └─────────────┘
  (Client)          (Application Server)    (DB Server)
```

**Real-World Analogy:**
Think of ordering food online:
- **Tier 1 (You)**: Use mobile app to browse menu and place order
- **Tier 2 (Restaurant)**: Kitchen prepares your food based on order
- **Tier 3 (Storage)**: Ingredients are stored in refrigerator/pantry

**Examples:**
- E-commerce websites (Amazon, Daraz)
- Social media (Facebook, Instagram)
- Banking websites
- Gmail, Yahoo Mail
- Netflix, YouTube

**Detailed Example - E-commerce Website:**

**Tier 1: Presentation Layer (Client)**
```html
<!DOCTYPE html>
<html>
<body>
    <h1>Online Shop</h1>
    <form action="/add-to-cart" method="POST">
        <input type="text" name="product_id" value="101">
        <input type="number" name="quantity">
        <button>Add to Cart</button>
    </form>
</body>
</html>
```
- User sees product catalog
- User clicks "Add to Cart"
- Browser sends request to application server

**Tier 2: Business Logic Layer (Application Server)**
```php
<?php
// Receives request from client
$product_id = $_POST['product_id'];
$quantity = $_POST['quantity'];
$user_id = $_SESSION['user_id'];

// Business Logic
if ($quantity > 0 && $quantity <= 10) {
    // Check if product is available
    $available = checkInventory($product_id, $quantity);

    if ($available) {
        // Calculate price
        $price = getProductPrice($product_id);
        $total = $price * $quantity;

        // Add to cart in database
        addToCart($user_id, $product_id, $quantity, $total);

        echo "Item added to cart!";
    } else {
        echo "Sorry, out of stock!";
    }
} else {
    echo "Invalid quantity!";
}
?>
```
- Validates user input
- Checks business rules
- Communicates with database

**Tier 3: Data Layer (Database Server)**
```sql
-- Products Table
CREATE TABLE products (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    price DECIMAL(10,2),
    stock INT
);

-- Cart Table
CREATE TABLE cart (
    user_id INT,
    product_id INT,
    quantity INT,
    total_price DECIMAL(10,2)
);

-- Query executed by application server
INSERT INTO cart (user_id, product_id, quantity, total_price)
VALUES (123, 101, 2, 1999.98);
```
- Stores all data
- Handles queries from application server
- Returns data to application server

**Communication Flow:**
```
1. User clicks "Add to Cart" → Browser
2. Browser sends HTTP POST → Application Server
3. Application Server validates data
4. Application Server sends SQL query → Database
5. Database executes query and responds
6. Application Server processes result
7. Application Server generates HTML
8. Application Server sends HTML → Browser
9. Browser displays "Item added to cart!"
```

**Advantages:**
- ✅ Separation of concerns (organized code)
- ✅ Easy to maintain and update
- ✅ Highly scalable
- ✅ Better security
- ✅ Reusable business logic
- ✅ Can update one tier without affecting others
- ✅ Better performance (specialized servers)
- ✅ Multiple clients can use same business logic

**Disadvantages:**
- ❌ More complex to develop
- ❌ Higher cost (multiple servers)
- ❌ Network latency (multiple hops)
- ❌ Requires more expertise
- ❌ Difficult to test

### 4. Multi-Tier Architecture (N-Tier)

**What is N-Tier Architecture?**

N-tier architecture extends three-tier by adding more specialized layers. Modern applications often have 4, 5, or more tiers for better organization, scalability, and security.

**Example Structure:**
```
┌──────────────┐
│ Presentation │ ← Web Browser (Client)
└──────┬───────┘
       │
┌──────▼───────┐
│ Web Server   │ ← Nginx/Apache (serves static files)
└──────┬───────┘
       │
┌──────▼───────┐
│ Application  │ ← Business Logic (Node.js/PHP/Java)
│   Server     │
└──────┬───────┘
       │
┌──────▼───────┐
│ API Layer    │ ← RESTful API
└──────┬───────┘
       │
┌──────▼───────┐
│ Database     │ ← MySQL/PostgreSQL
│   Server     │
└──────┬───────┘
       │
┌──────▼───────┐
│ File Storage │ ← Cloud Storage (AWS S3)
└──────────────┘
```

**Real-World Example - Social Media Platform:**
1. **CDN Layer**: Delivers images/videos quickly
2. **Load Balancer**: Distributes user requests
3. **Web Server**: Serves HTML/CSS/JavaScript
4. **Application Server**: Processes business logic
5. **Cache Layer**: Stores frequently accessed data (Redis)
6. **Database Server**: Stores user data, posts
7. **File Storage**: Stores photos, videos
8. **Search Server**: Powers search functionality (Elasticsearch)
9. **Notification Service**: Sends push notifications
10. **Analytics Server**: Tracks user behavior

**Advantages:**
- ✅ Highly scalable
- ✅ Flexible and modular
- ✅ Can use specialized servers for each function
- ✅ Fault tolerant
- ✅ Easy to update individual components

**Disadvantages:**
- ❌ Very complex
- ❌ Expensive
- ❌ Requires expert team
- ❌ Higher latency

### Comparison Table

| Feature | 1-Tier | 2-Tier | 3-Tier | N-Tier |
|---------|--------|--------|--------|--------|
| **Complexity** | Simple | Moderate | Complex | Very Complex |
| **Cost** | Low | Medium | High | Very High |
| **Scalability** | Poor | Limited | Good | Excellent |
| **Maintenance** | Hard | Moderate | Easy | Easy |
| **Performance** | Fast | Good | Good | Optimized |
| **Security** | Low | Medium | High | Very High |
| **Example** | MS Word | Desktop Apps | Web Apps | Enterprise Apps |
| **Best For** | Personal use | Small orgs | Businesses | Large enterprises |

### Summary

- **1-Tier**: Everything on one machine (offline apps)
- **2-Tier**: Client + Database (desktop applications)
- **3-Tier**: Client + Application Server + Database (web applications)
- **N-Tier**: Multiple specialized layers (enterprise applications)

Modern web applications typically use 3-tier or N-tier architecture for flexibility, scalability, and maintainability.
