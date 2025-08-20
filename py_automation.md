# 🔐 Automating Security in CI/CD with Python (DevSecOps)

## 📌 Overview

This project demonstrates how **Python** can be used to automate **security tasks inside CI/CD pipelines**, enabling a **DevSecOps culture** where security is built in — not added later.

By combining **Python automation** with modern CI/CD tools, you can:

* Find and fix vulnerabilities early
* Speed up secure releases
* Reduce manual security work
* Build confidence in your software delivery

---

## 🚀 Why Python for CI/CD Security?

* ⚡ **Speed & Efficiency** → Automated checks keep releases fast *and* secure
* 🛡️ **Early Detection** → Issues caught during development are cheaper to fix
* 📏 **Consistency** → Same rules applied across every build
* 👨‍💻 **Less Manual Work** → Security teams focus on bigger problems
* 🔄 **Security Culture** → Everyone in Dev + Ops + Sec is responsible

---

## 🔧 Security Tasks You Can Automate with Python

### 🧪 Security Testing

* **SAST (Static Application Security Testing)** → scan source code for vulnerabilities
* **DAST (Dynamic Application Security Testing)** → test running apps in staging environments
* **SCA (Software Composition Analysis)** → check 3rd party dependencies

### 🛡️ Vulnerability Scanning

* Scan **container images**, **infrastructure configs**, and pipelines
* Schedule scans and send alerts for new CVEs

### ✅ Compliance Checks

* Enforce **secure coding rules**
* Validate **infrastructure configs** against standards
* Auto-generate compliance reports

### 🔑 Secrets Management

* Detect **hardcoded credentials** in code
* Integrate with **HashiCorp Vault** to securely fetch/store secrets

### 📜 Policy Enforcement

* Apply **Policy-as-Code** to block builds if security rules are broken
* Example: Stop release if critical vulnerabilities are found

---

## ⚙️ Python + CI/CD Tools

Python integrates seamlessly with popular CI/CD systems:

* **Jenkins, GitLab CI, CircleCI** → run Python scripts as pipeline steps
* **API Connections** → use Python to trigger scans, fetch results, and manage builds
* **Extensions/Add-ons** → many plugins support Python automation

---

## 🛠️ Beyond Security

Python also helps automate:

* 🔨 **Environment Setup** → build secure staging/test environments
* 🧹 **Code Quality Checks** → run linters & style checkers early
* 📦 **Secure Releases** → enforce best practices for deployments

---

## 📚 Resources

* [Best Python Libraries for Cybersecurity in 2024](https://medium.com/@Scofield_Idehen/best-python-libraries-for-cybersecurity-in-2024-037a870f39d1)
* [Vulnerability Scanning for Secure Python Development (safety-cli)](https://safetycli.com/)
* [OWASP Dependency-Check and Vulnerability Scanning](https://www.linkedin.com/pulse/article-3-owasp-dependency-check-vulnerability-scanning-adorsys-p73fe)
* [Python library for Hashicorp Vault](https://discuss.hashicorp.com/t/python-library-for-hashicorp-vault-implementation/55805)
* [Continuous Integration With Python](https://realpython.com/python-continuous-integration/)
* [Python for DevOps: An Ultimate Guide](https://code-b.dev/blog/python-devops)
* [Building Custom Cybersecurity Tools with Python](https://www.linkedin.com/pulse/building-custom-cybersecurity-tools-python-bi6if)
* [Secure Coding in Python](https://www.linkedin.com/pulse/secure-coding-python-essential-practices-data-engineers-priyanka-sain-wewkc)

---

## ✅ Key Takeaways

* 🔄 **DevSecOps = Development + Security + Operations together**
* 🐍 **Python is the automation ally** that secures CI/CD pipelines
* 🏗️ Security should be **built-in**, not bolted on later
* 🚀 With Python + CI/CD, you can release **secure software faster**

---

# 🐍 Essential Python Components for Automation

Automation = using technology to reduce manual effort for repetitive tasks.
As a **security analyst**, Python is one of your most powerful tools for **automating security operations** such as:

* Investigating logins
* Managing access
* Updating devices
* Scanning logs

To automate effectively, you need to master a few **core Python building blocks**.

---

## 🔑 Core Python Components for Automation

### 1. Variables

* Containers that **store data** for reuse.
* Without variables, you’d have to hardcode values everywhere.

```python
username = "sur"
login_attempts = 3
```

---

### 2. Conditional Statements

* Evaluate conditions before performing actions.
* Save time vs manually checking every case.

```python
if login_attempts > 5:
    print("Alert! Too many login attempts.")
```

---

### 3. Iterative Statements (Loops)

* Repeat actions without retyping code.
* Two types: **for loops** (sequences) & **while loops** (conditions).

```python
# For loop
for user in ["alice", "bob", "sur"]:
    print(user)

# While loop
count = 0
while count < 3:
    print("Retrying...")
    count += 1
```

---

### 4. Functions

* Reusable blocks of code.
* Define once, use many times.

```python
def alert_user(user, attempts):
    if attempts > 3:
        print(f"⚠️ Security alert for {user}!")

alert_user("sur", 5)
```

---

### 5. Strings

* Strings are everywhere (usernames, logs, messages).
* Techniques: indexing, slicing, built-ins.

```python
s = "security"
print(s[0])      # 's'
print(len(s))    # 8
print(s.upper()) # 'SECURITY'
```

---

### 6. Lists

* Store multiple values in one container.
* Useful for logins, IPs, flagged users.

```python
users = ["alice", "bob", "sur"]
users.append("root")
print(users)  # ['alice', 'bob', 'sur', 'root']
```

---

## 🧑‍💻 Example: Counting Logins for a Flagged User

Imagine you’re asked to **check how many times a flagged user logged in today**.

```python
def count_logins(flagged_user, login_list):
    count = 0
    for user in login_list:
        if user == flagged_user:
            count += 1
    return count

# Example usage:
logins_today = ["alice", "sur", "bob", "sur", "sur", "alice"]
print(count_logins("sur", logins_today))  # Output: 3
```

✅ This combines:

* Variables (`count`)
* Iterative statements (`for loop`)
* Conditionals (`if user == flagged_user`)
* Functions (`count_logins()`)
* Lists (`logins_today`)

---

## 📂 Working with Files

Security data often lives in **log files**:

* `.txt` → plain text logs
* `.csv` → structured, comma-separated logs

You need to read/write these files to automate investigations.

```python
# Read a .txt file
with open("logins.txt", "r") as file:
    for line in file:
        print(line.strip())

# Read a .csv file
import csv
with open("logins.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

---

## ✅ Key Takeaways

* Python automation depends on **core concepts**:

  * Variables
  * Conditionals
  * Loops
  * Functions
  * Strings & Lists
* **Working with files** is essential, since most security data comes from logs.
* Together, these allow you to **automate security workflows** like scanning logs, enforcing access rules, and reporting suspicious activity.

---

### 🔑 Essentials for Files in Python

1. **Why security analysts need this**

   * Logs (`.txt`, `.csv`) = records of login attempts, attacks, app errors.
   * Analysts automate reading/parsing logs → detect anomalies & threats.
   * Writing to files = store results, create allow/deny lists, document findings.

---

2. **Opening files**

   ```python
   with open("update_log.txt", "r") as file:
   ```

   * `with` → manages file (auto-closes, safe from errors).
   * `open()` → opens the file.
   * First parameter → filename or file path.
   * Second parameter → mode:

     * `"r"` → read
     * `"w"` → write (overwrite or create new file)
     * `"a"` → append (add to end of file).
   * `as file` → assigns file handle to variable `file`.

---

3. **Reading a file**

   ```python
   with open("update_log.txt", "r") as file:
       updates = file.read()

   print(updates)
   ```

   * `.read()` → converts file content → string.
   * Now you can use string methods (`len()`, `.index()`, etc.).

---

4. **Writing to a file**

   ```python
   with open("update_log.txt", "w") as file:
       file.write("new log entry")
   ```

   * `"w"` → overwrite file.
   * `"a"` → append to file (keeps old content).
   * `.write()` → adds string data to the file.

---

✅ **Key takeaway**:

* `"r"` = read logs
* `"w"` = overwrite/create new
* `"a"` = append new data

Logs = strings + lists → automation.

---
Perfect, Sur 👌 this section is all about **parsing file contents** using `.split()` and `.join()`. Let me make it crisp for you so it’s easier to remember:

---

## 📝 Quick Notes: Working with Files in Python (Parsing)

### 🔑 Parsing = making data more readable

* For **Python code** → structured format (e.g., list instead of raw string).
* For **humans** → easier to analyze results.

---

### 1. **`.split()` → String ➝ List**

* Splits a string into a list, based on a character you provide.

```python
# Example 1: Split by comma
approved_users = "elarson,bmoreno,tshah"
approved_users = approved_users.split(",")
print(approved_users)
# 👉 ['elarson', 'bmoreno', 'tshah']

# Example 2: Split by whitespace (default)
removed_users = "wjaffrey jsoto abernard"
removed_users = removed_users.split()
print(removed_users)
# 👉 ['wjaffrey', 'jsoto', 'abernard']
```

✔ Useful for **logs** → split into parts, then loop with `for`.

---

### 2. **`.join()` → List ➝ String**

* Joins a list into a string, separated by what you choose.

```python
# Example 1: Join with commas
approved_users = ["elarson", "bmoreno", "tshah"]
approved_users = ",".join(approved_users)
print(approved_users)
# 👉 "elarson,bmoreno,tshah"

# Example 2: Join with newline
print("\n".join(["user1", "user2", "user3"]))
# 👉 user1
#    user2
#    user3
```

✔ Needed before writing lists back into a file (since `.write()` expects a string).

---

### 3. **Using `.split()` & `.join()` with files**

```python
# Read and split file contents
with open("update_log.txt", "r") as file:
    updates = file.read()

updates = updates.split()  # String → List

# Do operations on updates...

# Join and write back
updates = " ".join(updates)  # List → String
with open("update_log.txt", "w") as file:
    file.write(updates)
```

---

### 🚀 Key Takeaways

* `.split()` = string ➝ list (default split by whitespace, or give your own separator like `","`).
* `.join()` = list ➝ string (you pick the separator like `","` or `"\n"`).
* Together, they let you **parse logs**, **analyze them**, and **save results**.

---

