## Bandit Level 00 → Level 01


### 🎯 Objective  

- Log in to the Bandit game using the given credentials  
- Locate the `readme` file  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit0`  
- List the files  
- Read the `readme` file  
- Extract the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit0  
- **Password:** bandit0  


---

### 🔍 Method of Solve  

The password for the next level is stored in a file named `readme` inside the home directory.  
By listing the files and reading the file contents, the password can be obtained.

Steps followed:  
- List all files  
- Read the `readme` file  


---

### 🧪 Commands Used  

- `ls`  
- `cat readme`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `ls` | Lists the files in the directory |
| `cat readme` | Displays the content of the password file |


---

### 📸 Screenshot Evidence  

![Bandit Level 00 Screenshot](screenshots/level00.png)


---

### 🔑 Next Level Password  

```
ZjlJTmM6FvvyRnrB2rfNWOZOTa6ip5If
```


---

### 🧠 Explanation  

- The `ls` command lists available files  
- The `readme` file contains the password  
- `cat readme` displays the password on screen  


---

### 🔐 Concept Learned  

This level introduces basic Linux file access.  
It shows how sensitive data can be stored in simple text files.


---

### 🛡️ Security Insight  

Passwords stored in plain text files are highly insecure.  
Proper access controls and encryption should always be used.
