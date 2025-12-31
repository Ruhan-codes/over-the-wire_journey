## Bandit Level 22 → Level 23

### 🎯 Objective
Abuse the cron job to retrieve the password for bandit23.

### 🔑 Credentials Provided
Username: bandit22  
Password: EeoULMCra2q0qDsKyj5l6lDX7s1CpBuOBt  

### 🔍 Method of Solve
Inside /etc/cron.d there is a cron job that runs as bandit23.  
The cron script copies bandit23’s password into /tmp but with an md5-based filename.  
We just need to:
1) View cron job  
2) See what filename is generated  
3) Read the file in /tmp

### 🧪 Commands Used
cd /etc/cron.d  
cat cronjob_bandit23  
cat /usr/bin/cronjob_bandit23.sh  
echo I am user bandit23 | md5sum  
cat /tmp/<hash>

### 📸 Screenshot (Paste here)

### 🧠 Explanation
The cronjob script does:
myname=$(whoami)  
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)  
It then copies password from /etc/bandit_pass/bandit23 → /tmp/<hash>
So we generate the same md5:
echo I am user bandit23 | md5sum  
This gives:
8ca319486bfbb3663ea0fbe813236349  
Then simply read:
cat /tmp/8ca319486bfbb3663ea0fbe813236349  

### 🔐 Next Level Password
8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

### ✅ Concept Learned
• Cron jobs execution  
• md5 hashing usage  
• Privilege escalation logic  
• Using /tmp exploitation
