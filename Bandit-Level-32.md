
## Bandit Level 32 → Level 33


### 🎯 Objective  

- Log in as `bandit32`  
- Escape the uppercase-only shell  
- Launch a normal Bash shell  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit32`  
- Execute `$0` to escape the restricted shell  
- Start `bash`  
- Read the password file  


---

### 🔑 Credentials Provided  

- **Username:** bandit32  
- **Password:** 309RfhaqALVBEZpVb6LYStshZoqoSx5K  


---

### 🔍 Method of Solve  

The `bandit32` account uses a shell that only accepts uppercase input.  
By executing the `$0` environment variable, the restricted shell is replaced with a normal shell, allowing standard commands to be run.

Steps followed:  
- Execute `$0`  
- Start a Bash shell  
- Read the password file  


---

### 🧪 Commands Used  

- `$0`  
- `bash`  
- `cat /etc/bandit_pass/bandit33`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `$0` | Spawns a new instance of the current shell |
| `bash` | Starts a normal Bash shell |
| `cat bandit33` | Displays the next level password |


---

### 📸 Screenshot Evidence  

**Escaping the Uppercase Shell and Reading the Password**  
![Bandit Level 32 Screenshot](screenshots/level32.png)


---

### 🔑 Next Level Password  

```
tQdtbs5D5i2vJwk08mEyYETL81z0eJ0
```


---

### 🧠 Explanation  

- `$0` launches a new shell without the uppercase restriction  
- `bash` starts a standard interactive shell  
- The password file is read using `cat`  


---

### 🔐 Concept Learned  

This level shows how restricted shells can be bypassed.  
It highlights how environment variables can be leveraged to escape limited environments.


---

### 🛡️ Security Insight  

Shell restrictions must be carefully implemented.  
Weak restrictions can be bypassed using built-in shell features.
