## Bandit Level 19 → Level 20

### 🎯 Objective
Gain the password for bandit20 by using the setuid binary provided in the home directory.

---

### 🔑 Credentials Provided
- **Username:** bandit19  
- **Password:** Obtained from previous level  

---

### 🔍 Method of Solve
The level provides a special binary named `bandit20-do` which has the SUID bit set.  
This binary allows executing a command **as the user bandit20**, meaning we can use it to read the next level’s password file that is normally not accessible.

First attempt failed because the command was not executed with the correct path.  
Running the binary with `./` executes it properly.

---

### 🧪 Commands Used
- `ls -la`  
  Displays files in the directory and confirms `bandit20-do` has SUID permissions.

- `./bandit20-do cat /etc/bandit_pass/bandit20`  
  Executes the binary as bandit20 and prints the password for the next level.

---

### 🖼 Screenshot
![Bandit Level 19 Screenshot](screenshots/level19.png)

---

### 🔑 Next Level Password
`oQXahG8ZJ0VMN9Ghs7iOWscfZyXOUbY0`

---

### 🧠 Explanation
The SUID permission allows a program to run with the privileges of the file owner.  
Since `bandit20-do` is owned by bandit20, executing it lets us run commands as bandit20 and retrieve the protected password file.

---

### 🔐 Concept Learned
- Understanding and exploiting SUID binaries
- Running executables with relative paths (`./filename`)
