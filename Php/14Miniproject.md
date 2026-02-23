 ---

# 📘 UNIT – 14 : MINI PROJECT (PHP + MySQL + OOP) — DETAILED

This unit is about **building**, not just learning.
After this, you can confidently say:

> “I can build a PHP backend application.”

---

## 🎯 Project Title

### **Student Management System (SMS)**

You can later extend this to:

* College portal
* Admin dashboard
* Learning platform (fits your long-term goals 👌)

---

## 🧠 What You Will Learn from This Project

* PHP (procedural + OOP)
* Forms & validation
* Sessions (login system)
* PHP + MySQL (CRUD)
* Folder structure (professional)
* Basic security

---

## 🧱 Project Features

### 👤 Authentication

* Admin login
* Session-based access
* Logout

### 📚 Student Management (CRUD)

* Add student
* View students
* Update student
* Delete student

---

## 🗂️ Project Folder Structure (VERY IMPORTANT 🔥)

```
student_management/
│
├── config/
│   └── db.php
│
├── classes/
│   └── Student.php
│
├── auth/
│   ├── login.php
│   ├── login_process.php
│   └── logout.php
│
├── students/
│   ├── add.php
│   ├── view.php
│   ├── edit.php
│   └── delete.php
│
├── dashboard.php
└── index.php
```

👉 This structure is **industry-style**, not random files.

---

## 🗄️ Database Design

### Database

```sql
CREATE DATABASE sms;
USE sms;
```

### Admin Table

```sql
CREATE TABLE admin (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50),
    password VARCHAR(255)
);
```

### Student Table

```sql
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    email VARCHAR(50),
    branch VARCHAR(20)
);
```

---

## 🔌 Database Connection (`config/db.php`)

```php
<?php
$conn = mysqli_connect("localhost", "root", "", "sms");

if (!$conn) {
    die("Database connection failed");
}
?>
```

---

## 🧩 Student Class (OOP) – `classes/Student.php`

```php
<?php
class Student {
    private $conn;

    function __construct($db) {
        $this->conn = $db;
    }

    function add($name, $email, $branch) {
        $sql = "INSERT INTO students (name, email, branch)
                VALUES (?, ?, ?)";
        $stmt = mysqli_prepare($this->conn, $sql);
        mysqli_stmt_bind_param($stmt, "sss", $name, $email, $branch);
        return mysqli_stmt_execute($stmt);
    }

    function getAll() {
        return mysqli_query($this->conn, "SELECT * FROM students");
    }

    function delete($id) {
        $stmt = mysqli_prepare($this->conn,
            "DELETE FROM students WHERE id=?");
        mysqli_stmt_bind_param($stmt, "i", $id);
        return mysqli_stmt_execute($stmt);
    }
}
?>
```

✔ OOP
✔ Prepared statements
✔ Secure

---

## 🔐 Login System (Session-Based)

### `auth/login_process.php`

```php
<?php
session_start();
include "../config/db.php";

$user = $_POST["username"];
$pass = $_POST["password"];

$result = mysqli_query($conn,
    "SELECT * FROM admin WHERE username='$user'");

$row = mysqli_fetch_assoc($result);

if ($row && password_verify($pass, $row["password"])) {
    $_SESSION["admin"] = $user;
    header("Location: ../dashboard.php");
} else {
    echo "Invalid login";
}
?>
```

---

## 🧠 Session Protection (VERY IMPORTANT)

```php
<?php
session_start();
if (!isset($_SESSION["admin"])) {
    header("Location: auth/login.php");
    exit();
}
?>
```

Use this on **every protected page**.

---

## 📄 Add Student (`students/add.php`)

```php
<?php
include "../config/db.php";
include "../classes/Student.php";

$student = new Student($conn);

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $student->add(
        $_POST["name"],
        $_POST["email"],
        $_POST["branch"]
    );
    echo "Student added";
}
?>
```

---

## 👀 View Students (`students/view.php`)

```php
<?php
include "../config/db.php";
include "../classes/Student.php";

$student = new Student($conn);
$data = $student->getAll();

while ($row = mysqli_fetch_assoc($data)) {
    echo $row["name"] . " - " . $row["branch"] . "<br>";
}
?>
```

---

## 🧠 Project Flow (Big Picture)

```
Login
  ↓
Session Created
  ↓
Dashboard
  ↓
Student CRUD
  ↓
Database
```

![Image](https://user-images.githubusercontent.com/59060634/89009944-48673800-d32b-11ea-82f9-1bbaec9521ef.PNG)

![Image](https://www.php.net/manual/en/images/f3bc48edf40d5e3e09a166c7fadc7efb-driver_arch.svg)

![Image](https://media2.dev.to/dynamic/image/width%3D1000%2Cheight%3D420%2Cfit%3Dcover%2Cgravity%3Dauto%2Cformat%3Dauto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Femzu1zhk8kcr5bypbnvw.jpg)

---

## 🔐 Security Used in Project

* Prepared statements
* Password hashing
* Session protection
* Input validation

---

## ✍️ UNIT–14 EXAM SHORT NOTES

* Mini projects integrate all PHP concepts
* OOP improves structure
* CRUD is core of applications
* Sessions handle authentication
* MySQL stores permanent data

---

## 🧪 How to Extend This Project (VERY IMPORTANT 🚀)

You can add:

* Edit student
* Search student
* Pagination
* Roles (admin/user)
* Bootstrap UI
* Hosting (000webhost)

---
