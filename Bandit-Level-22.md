
## Bandit Level 22 → Level 23


### 🎯 Objective  

- Log in as `bandit22`  
- Analyze the cron job  
- Reproduce the filename generation logic  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit22`  
- Inspect the cron configuration  
- Read the cron script  
- Recreate the MD5-based filename  
- Read the password file  


---

### 🔑 Credentials Provided  

- **Username:** bandit22  
- **Password:** tRaeOUfB9vOUZbCdn9cY0qNds9GF58Q  


---

### 🔍 Method of Solve  

A cron job runs as `bandit23` and stores the password in a file inside `/tmp` with a dynamically generated name.  
By reading the cron script, the logic used to create the filename can be identified and reproduced.

Steps followed:  
- Navigate to the cron configuration directory  
- Inspect the cron job and script  
- Recreate the filename using the same logic  
- Read the generated file  


---

### 🧪 Commands Used  

- `cd /etc/cron.d`  
- `ls -la`  
- `cat cronjob_bandit23`  
- `cat /usr/bin/cronjob_bandit23.sh`  
- `echo I am user bandit23 | md5sum`  
- `cat /tmp/<md5_hash>`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `cat cronjob_bandit23` | Shows the cron schedule |
| `cat cronjob_bandit23.sh` | Displays the script that generates the filename |
| `md5sum` | Generates the hash used in the filename |
| `cat /tmp/<md5_hash>` | Reads the password file |


---

### 📸 Screenshot Evidence  

![Bandit Level 22 Screenshot](screenshots/level22.png)


---

### 🔑 Next Level Password  

```
oZf11IOIjMVN55iJX3CmStKLYqjk54Ga
```


---

### 🧠 Explanation  

- The cron job creates a filename using an MD5 hash of a fixed string  
- Reproducing the same hash reveals the exact file name  
- Reading the file reveals the password for the next level  


---

### 🔐 Concept Learned  

This level demonstrates how predictable filename generation can expose sensitive data.  
It highlights the importance of using secure randomization for temporary files.


---

### 🛡️ Security Insight  

Weakly generated temporary file names can be guessed and exploited.  
Secure random file naming should always be used for sensitive outputs.
