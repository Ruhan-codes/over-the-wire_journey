
## Bandit Level 21 → Level 22


### 🎯 Objective  

- Log in as `bandit21`  
- Inspect the cron job  
- Identify where the password is written  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit21`  
- Review cron configuration files  
- Read the cron script  
- Locate the output file  
- Extract the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit21  
- **Password:** Ee0ULMCrq2q0dSKYj561DX7s1CpBuOBt  


---

### 🔍 Method of Solve  

A cron job runs periodically as `bandit22`.  
By inspecting the cron configuration and the script it executes, the file where the password is stored can be identified.

Steps followed:  
- Navigate to the cron directory  
- Read the cron job configuration  
- Inspect the executed script  
- Read the output file  


---

### 🧪 Commands Used  

- `cd /etc/cron.d`  
- `ls -la`  
- `cat cronjob_bandit22`  
- `cat /usr/bin/cronjob_bandit22.sh`  
- `cat /tmp/t706lds9S0Rq9h9aMcz6ShpAoZKF7fgv`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `cat cronjob_bandit22` | Shows the cron schedule and command |
| `cat cronjob_bandit22.sh` | Displays the script run by cron |
| `cat /tmp/...` | Reads the file containing the password |


---

### 📸 Screenshot Evidence  

![Bandit Level 21 Screenshot](screenshots/level21.png)


---

### 🔑 Next Level Password  

```
tRaeOUfB9vOUZbCdn9cY0qNds9GF58Q
```


---

### 🧠 Explanation  

- The cron job runs a script as `bandit22`  
- The script copies the password into a temporary file  
- Reading that file reveals the password for the next level  


---

### 🔐 Concept Learned  

This level demonstrates how cron jobs can expose sensitive data.  
It shows why temporary files created by scheduled tasks must be properly secured.


---

### 🛡️ Security Insight  

Improperly protected cron outputs can leak credentials.  
System administrators must restrict access to scheduled task outputs.
