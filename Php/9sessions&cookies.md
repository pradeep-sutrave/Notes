
# 📘 UNIT – 9 : SESSIONS & COOKIES IN PHP (DETAILED)

This unit is the **backbone of login systems, authentication, and user tracking**.

---

## 1️⃣ Why Sessions & Cookies Are Needed?

HTTP is **stateless** ❌
That means:

* Server **does not remember** users between requests
* Every page load is treated as **new**

👉 Sessions & cookies solve this problem.

---

## 2️⃣ What is a Session?

### Definition (Exam-ready ✍️)

> A session is a way to store user data on the **server** so that it can be accessed across multiple pages.

### Key Points

* Data stored on **server**
* Identified using a **session ID**
* Secure compared to cookies
* Used for **login systems**

---

## 3️⃣ What is a Cookie?

### Definition (Exam-ready ✍️)

> A cookie is a small piece of data stored in the **user’s browser**.

### Key Points

* Data stored on **client (browser)**
* Has expiry time
* Less secure
* Used for **remember me**, preferences

---

## 4️⃣ Session vs Cookie (VERY IMPORTANT 🔥)

| Feature   | Session             | Cookie        |
| --------- | ------------------- | ------------- |
| Stored on | Server              | Browser       |
| Security  | High                | Low           |
| Expiry    | When browser closes | Fixed time    |
| Size      | Large               | Small         |
| Use       | Login, auth         | Remember user |

---

## 5️⃣ How Sessions Work (Concept)

```
User Login
   ↓
Server creates Session ID
   ↓
Session ID stored in browser (cookie)
   ↓
User visits another page
   ↓
Server matches Session ID
   ↓
User data retrieved
```

![Image](https://www.sitesbay.com/php/images/session-in-php.png)

![Image](https://cms-assets.tutsplus.com/cdn-cgi/image/width%3D850/uploads/users/413/posts/36546/image-upload/session_1.png)

![Image](https://svg.template.creately.com/imrlwe5x1)

---

## 6️⃣ Starting a Session

⚠️ **Mandatory rule**:
`session_start()` must be **first line**, before HTML.

```php
<?php
session_start();
?>
```

---

## 7️⃣ Creating & Using Session Variables

```php
<?php
session_start();

$_SESSION["username"] = "Bhupathi";
$_SESSION["role"] = "student";

echo $_SESSION["username"];
?>
```

✔ Stored on server
✔ Available on all pages

---

## 8️⃣ Accessing Session on Another Page

```php
<?php
session_start();

echo "Welcome " . $_SESSION["username"];
?>
```

---

## 9️⃣ Destroying a Session (Logout)

### Logout Logic

```php
<?php
session_start();
session_unset();   // remove all session variables
session_destroy(); // destroy session
?>
```

📌 Used when user logs out

---

## 🔟 Complete Login System Using Sessions (Mini Demo 🔥)

### `login.php`

```html
<form method="post" action="login_process.php">
    Username: <input type="text" name="user"><br>
    Password: <input type="password" name="pass"><br>
    <input type="submit" value="Login">
</form>
```

---

### `login_process.php`

```php
<?php
session_start();

$username = $_POST["user"];
$password = $_POST["pass"];

if ($username == "admin" && $password == "1234") {
    $_SESSION["user"] = $username;
    header("Location: dashboard.php");
} else {
    echo "Invalid login";
}
?>
```

---

### `dashboard.php`

```php
<?php
session_start();

if (!isset($_SESSION["user"])) {
    header("Location: login.php");
    exit();
}

echo "Welcome " . $_SESSION["user"];
?>
```

---

### `logout.php`

```php
<?php
session_start();
session_destroy();
header("Location: login.php");
?>
```

---

## 1️⃣1️⃣ Cookies in PHP

### Creating a Cookie

```php
<?php
setcookie("user", "Bhupathi", time() + 3600);
?>
```

📌 Cookie expires in **1 hour**

---

### Accessing Cookie

```php
<?php
echo $_COOKIE["user"];
?>
```

---

### Deleting Cookie

```php
<?php
setcookie("user", "", time() - 3600);
?>
```

---

## 1️⃣2️⃣ Cookie Example (Remember Me)

```php
<?php
setcookie("remember_user", "Bhupathi", time() + (86400 * 7));
?>
```

✔ Remembers user for 7 days

---

## 1️⃣3️⃣ Session Security Best Practices 🔐

* Always use `session_start()`
* Regenerate session ID after login

```php
session_regenerate_id(true);
```

* Destroy session on logout
* Never store passwords directly

---

## 1️⃣4️⃣ When to Use What?

✔ **Use Session when**:

* Login authentication
* Sensitive data
* User roles

✔ **Use Cookie when**:

* Remember me
* Language preference
* Theme selection

---

## ✍️ UNIT–9 EXAM SHORT NOTES

* Sessions store data on server
* Cookies store data in browser
* `session_start()` initializes session
* Sessions are more secure
* Cookies have expiry time

---

## 🧪 Practice Questions (VERY IMPORTANT 💪)

1️⃣ Create login system using session
2️⃣ Protect dashboard page
3️⃣ Implement logout
4️⃣ Create remember-me cookie

---
