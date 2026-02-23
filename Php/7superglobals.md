
# 📘 UNIT – 7 : PHP SUPERGLOBALS (DETAILED)

Superglobals are **predefined variables in PHP** that are **accessible anywhere** in the script — inside functions, outside functions, anywhere.

👉 They are the **bridge between user, browser, server, and PHP**.

---

## 1️⃣ What are Superglobals?

### Definition (Exam-ready ✍️)

> Superglobals are built-in PHP variables that are always available and used to collect form data, server data, session data, and cookies.

---

## 2️⃣ List of PHP Superglobals

| Superglobal | Purpose                 |
| ----------- | ----------------------- |
| `$GLOBALS`  | Access global variables |
| `$_GET`     | Get data from URL       |
| `$_POST`    | Get data from forms     |
| `$_REQUEST` | GET + POST              |
| `$_SERVER`  | Server information      |
| `$_SESSION` | Store user session data |
| `$_COOKIE`  | Store data in browser   |
| `$_FILES`   | Handle file uploads     |
| `$_ENV`     | Environment variables   |

![Image](https://www.easytolearning.com/webroot/ck_files/files/SuperGlobales-Variables-in-PHP.png)

![Image](https://cms-assets.tutsplus.com/cdn-cgi/image/width%3D360/uploads/users/413/posts/36575/image-upload/how-to-work-with-cookies-in-php-stateful-http-protocol.png)

![Image](https://imgv2-1-f.scribdassets.com/img/document/964991140/original/6882fa74b3/1?v=1)

---

# 🔹 1. `$GLOBALS`

Used to access **global variables inside functions**.

```php
<?php
$x = 10;
$y = 20;

function add() {
    $GLOBALS['sum'] = $GLOBALS['x'] + $GLOBALS['y'];
}

add();
echo $sum;
?>
```

📌 Without `$GLOBALS`, global variables are not accessible inside functions.

---

# 🔹 2. `$_GET`

Used to collect data sent through **URL**.

### Example URL

```
http://localhost/test.php?name=Bhupathi&age=20
```

### PHP Code

```php
<?php
echo $_GET["name"];
echo $_GET["age"];
?>
```

✔ Data visible in URL
❌ Not secure for passwords


---

## 🔹 What is `isset()` in PHP?

`isset()` is used to **check whether a variable exists AND is not `NULL`**.

### 👉 It returns:

* `true` → variable exists & has a value
* `false` → variable does not exist OR is `NULL`

---

## 🧠 Basic Syntax

```php
isset(variable)
```

---

## ✅ Why `isset()` is IMPORTANT

Without `isset()`, PHP may throw **warnings/notices** like:

> ⚠️ Undefined index
> ⚠️ Undefined variable

`isset()` prevents these.

---

## 🔸 Example 1: Normal Variable

```php
$a = 10;

if (isset($a)) {
    echo "Variable exists";
}
```

✔ Output:

```
Variable exists
```

---

## 🔸 Example 2: Undefined Variable

```php
if (isset($b)) {
    echo "b exists";
}
```

❌ Nothing prints (no warning!)

---

## 🔸 Example 3: Form Data (MOST COMMON USE)

```php
if (isset($_POST['name'])) {
    echo $_POST['name'];
}
```

### Without `isset()` ❌

```php
echo $_POST['name']; // ⚠️ Warning if form not submitted
```

---

## 🔸 Example 4: `$_GET`

```php
// URL: page.php?age=20
if (isset($_GET['age'])) {
    echo $_GET['age'];
}
```

---

## 🔸 Example 5: Multiple Variables

```php
if (isset($_GET['name'], $_GET['age'])) {
    echo "Both exist";
}
```

---

## ❓ `isset()` vs `empty()` (Very Important)

| Feature                  | `isset()` | `empty()` |
| ------------------------ | --------- | --------- |
| Checks variable exists   | ✅         | ✅         |
| Checks NULL              | ❌ (false) | ✅         |
| Checks empty string `""` | ✅         | ❌         |
| Checks `0`               | ✅         | ❌         |

### Example:

```php
$a = 0;

isset($a);  // true
empty($a);  // true
```

---

## 🔥 Real-Life Analogy

Think of `isset()` like:

> “Does this box exist, and is it not empty?”

---

## ✅ When to Use `isset()`

✔ Handling form data
✔ Avoiding PHP warnings
✔ Checking GET/POST/SESSION/COOKIE
✔ Writing clean, professional code

---

## ❌ When NOT to Use `isset()`

❌ To check **value correctness**
❌ To validate input (use conditions instead)

---


# 🔹 3. `$_POST` (🔥 VERY IMPORTANT)

Used to collect data from **HTML forms securely**.

### HTML Form

```html
<form method="post" action="submit.php">
    Name: <input type="text" name="name">
    <input type="submit">
</form>
```

### `submit.php`

```php
<?php
echo "Welcome " . $_POST["name"];
?>
```

✔ Data hidden
✔ Used for login, signup, forms

---

# 🔹 4. `$_REQUEST`

Collects data from **GET + POST**.

```php
<?php
echo $_REQUEST["name"];
?>
```

⚠️ Not recommended for secure applications.

---

# 🔹 5. `$_SERVER`

Stores **server and request information**.

```php
<?php
echo $_SERVER["SERVER_NAME"];     // localhost
echo $_SERVER["REQUEST_METHOD"];  // GET or POST
echo $_SERVER["PHP_SELF"];        // current file
?>
```

### Common Uses

* Detect request type
* Page routing
* Security checks

---

# 🔹 6. `$_SESSION` (🔥 VERY IMPORTANT)

Used to store **user data across pages**.

### Create Session

```php
<?php
session_start();
$_SESSION["user"] = "Bhupathi";
?>
```

### Access Session

```php
<?php
session_start();
echo $_SESSION["user"];
?>
```

✔ Data stored on server
✔ Used in login systems

---

# 🔹 7. `$_COOKIE`

Used to store data in **user’s browser**.

```php
<?php
setcookie("user", "Bhupathi", time() + 3600);
echo $_COOKIE["user"];
?>
```

✔ Lightweight storage
❌ Less secure than sessions

---

# 🔹 8. `$_FILES`

Used for **file upload handling**.

```php
<?php
$fileName = $_FILES["file"]["name"];
$fileTmp  = $_FILES["file"]["tmp_name"];
?>
```

Used for:

* Upload images
* Upload documents

---

# 🔹 9. `$_ENV`

Stores **environment variables**.

```php
<?php
print_r($_ENV);
?>
```

📌 Rarely used at beginner level.

---

## 🔁 GET vs POST (Quick Comparison)

| Feature      | GET     | POST         |
| ------------ | ------- | ------------ |
| Data visible | Yes     | No           |
| Security     | Low     | High         |
| URL length   | Limited | Unlimited    |
| Usage        | Search  | Login, forms |

---

## 🧠 Real-World Flow (Login Example)

```
HTML Form
   ↓
$_POST
   ↓
PHP Logic
   ↓
$_SESSION
   ↓
Dashboard
```

---

## ✍️ UNIT–7 EXAM SHORT NOTES

* Superglobals are always accessible
* `$_GET` gets data from URL
* `$_POST` is secure for forms
* `$_SESSION` stores server-side data
* `$_COOKIE` stores client-side data

---

## 🧪 Practice Questions (Important 💪)

1️⃣ Create a form using POST  
2️⃣ Display submitted name & branch  
3️⃣ Store username in session  
4️⃣ Check request method using `$_SERVER`  

---