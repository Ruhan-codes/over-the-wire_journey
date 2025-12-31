## Bandit Level 32 → Level 33

### 🎯 Objective  
Bypass the **uppercase-only restricted shell** and retrieve the password for the next level from  
`/etc/bandit_pass/bandit33`.

---

### 🔑 Credentials Provided  
- **Username:** bandit32  
- **Password:** From previous level

---

### 🔍 Method of Solve  
1. When logging in, you are placed inside an **uppercase shell** where only uppercase commands are allowed.
2. Normal lowercase Linux commands such as `ls`, `cat`, `bash`, etc., are blocked.
3. However, the shell can still execute lowercase binaries if we spawn a normal shell.
4. The trick is to execute **bash** (which is lowercase) directly, bypassing the uppercase restriction.
5. Once inside a real shell, simply read the password file.

---

### 🧪 Commands Used
```bash
$ bash
cat /etc/bandit_pass/bandit33
```

---

### 🧠 Explanation  
The provided shell forces uppercase execution and blocks standard commands.  
However, the system does not restrict **running an interactive bash shell**, which drops you into a normal unrestricted environment.  
Once inside bash, you can freely execute any commands and access the password file.

---

### 📸 Screenshot Placement  
(Place screenshot showing the `bash` escape and successful `cat` output)

---

### 🔐 Next Level Password  
`tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0`

---

### 🧠 Concept Learned  
- Restricted shells and how to bypass them  
- Spawning subshells to regain execution freedom  
- Accessing protected system files once restrictions are bypassed  
