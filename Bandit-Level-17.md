## Bandit Level 17 → Level 18

### 🎯 Objective
Log in as bandit17 and obtain the password for bandit18 by identifying the difference between two password files.

---

### 🔑 Credentials Provided
- **Username:** bandit17  
- **Authentication:** SSH Private Key from previous level

---

### 🔍 Method of Solve
Inside the home directory, two files are available:  
- `passwords.old`
- `passwords.new`

Only **one line** differs between them.  
The line present in `passwords.new` but not in `passwords.old` contains the password for the next level.

We use the `diff` command to compare both files and extract the changed line.

---

### 🧪 Commands Used
- `ls`
  Lists available files

- `diff passwords.new passwords.old`
  Compares both files and displays the difference

---

### 🖼 Screenshot
![Bandit Level 17 Screenshot](screenshots/level17.png)

---

### 🔑 Next Level Password
`x2gLTTjFwMOhQ80WNbMN362QKxfRqcGLo`

---

### 🧠 Explanation
The `diff` command compares files line by line.  
The output indicates which line differs.  
The highlighted line from `passwords.new` is the valid password for the next level.

---

### 🔐 Concept Learned
- File comparison using `diff`
- Understanding file difference indicators
- Identifying modified data between versions
