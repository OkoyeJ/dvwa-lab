# 🔐 DVWA Hacking Lab - Web Security Exploits

This project documents hands-on exploitation of common web vulnerabilities using the **Damn Vulnerable Web Application (DVWA)**. It is part of my cybersecurity analyst learning path and showcases practical skills in identifying and exploiting:

- ✅ Brute Force Login
- ✅ SQL Injection
- ✅ Cross-Site Scripting (XSS)

---

## ⚙️ Setup

DVWA was installed and configured locally using XAMPP on Windows.

1. Started Apache and MySQL via XAMPP Control Panel.
2. Accessed DVWA via: `http://localhost/dvwa/`
3. Created/Reset the database and logged in (`admin/password`)
4. Set security level to **Low**.

---

## 🔓 1. Brute Force Login

**Script:** [`bruteforce.py`](./bruteforce.py)

- Sent POST requests to DVWA's login form with a list of common passwords.
- Successfully found the password for the `admin` user.
- Used session cookies (`PHPSESSID`) to maintain login session.


---

## 💉 2. SQL Injection

**Tested Input:**
```sql
1' OR '1'='1

Result: Retrieved user details without authentication.
Used UNION SELECT to extract:

1' UNION SELECT null, version() -- 


⚠️ 3. Cross-Site Scripting (XSS)
Reflected XSS Payload:

<script>alert("XSS")</script>

Stored XSS Payload:

<script>alert("Stored XSS")</script>

Outcome: JavaScript executed in browser, confirming vulnerability.


🛡️ Mitigation Ideas
Use prepared statements to prevent SQLi.

Sanitize and escape user input for XSS.

Rate-limit and implement CAPTCHA to prevent brute-force.


🧠 Lessons Learned
How web app vulnerabilities can be exploited in real-world apps.

How important it is to validate and sanitize inputs.

Building and automating attack tools with Python.

🚀 About Me
I'm a cybersecurity enthusiast focused on learning real-world attack techniques in controlled environments.
This is part of my portfolio to demonstrate practical security testing skills.
 
 
