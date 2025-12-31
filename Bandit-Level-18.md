## Bandit Level 18 → Level 19

### 🎯 Objective
Log in as bandit18 and retrieve the password for bandit19.  
However, the normal login shell immediately logs the user out.  
We must bypass the shell restriction and read the `readme` file.

---

### 🔑 Credentials Provided
- **Username:** bandit18  
- **Password:** Obtained from previous level  

---

### 🔍 Method of Solve
Logging in normally kicks you out instantly.  
To bypass this, instead of starting an interactive shell, we execute the command directly during SSH login.

Using the `ssh` command with the `cat readme` argument allows us to run the command before the forced logout occurs.  
This prints the password successfully.

---

### 🧪 Commands Used
- `ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme`
  Connects to the server and directly executes `cat readme` to display the password before logout.

---

### 🖼 Screenshot
![Bandit Level 18 Screenshot](screenshots/level18.png)

---

### 🔑 Next Level Password
`cGWpMakXVVwDUNGpAVJBWYUGHVn9zL3j8`

---

### 🧠 Explanation
Bandit18 uses a restricted shell that disconnects immediately after login.  
Executing the command directly via SSH bypasses the login shell, allowing file access.

---

### 🔐 Concept Learned
- Bypassing restricted shells using command execution in SSH
- Direct remote command execution technique
