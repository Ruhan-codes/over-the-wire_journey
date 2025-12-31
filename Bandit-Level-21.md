## Bandit Level 21 → Level 22

### 🎯 Objective  
Exploit an automated cron job to retrieve the password for the next level.

---

### 🔑 Credentials Provided  
Username: bandit21  
Password: EeoULMCra2q0qDsKyj5l6lDX7s1CpBuOBt  

---

### 🔍 Method of Solve  
1. Check the cron jobs in `/etc/cron.d/` to see scheduled automated tasks.  
2. Identify the cron job belonging to `bandit22`.  
3. Read the executed script to understand what it does.  
4. Notice that the script copies the password file of bandit22 into a temporary world-readable location.  
5. Read the dumped password file.

---

### 🧪 Commands Used  
```bash
ls -la /etc/cron.d
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9s0QRQh9aMcz6ShpAoZKF7Fgv
