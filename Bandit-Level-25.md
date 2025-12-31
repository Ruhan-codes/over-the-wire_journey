## Bandit Level 25 → Level 26

### 🎯 Objective  
Login to bandit26 using the SSH private key found on the server and retrieve the password for the next level.

---

### 🔑 Credentials Provided  
- **Current User:** bandit25  
- **Authentication:** Password from previous level  
- **Given File:** `bandit26.sshkey` (PEM RSA Private Key)

---

### 🔍 Method of Solve  
1. Identify the SSH private key file in the bandit25 home directory.  
2. Transfer the key securely to your local Kali machine using SCP.  
3. Set proper permissions on the key to avoid SSH security restrictions.  
4. Use the key to SSH into bandit26.  
5. Once logged in, read the password file from `/etc/bandit_pass/`.

---

### 🧪 Commands Used  
```bash
# On bandit25 machine
ls
file bandit26.sshkey

# From local Kali machine
scp -P 2220 bandit25@bandit.labs.overthewire.org:/home/bandit25/bandit26.sshkey .

# Fix permissions
chmod 600 bandit26.sshkey

# SSH into bandit26
ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220

# Inside bandit26
cat /etc/bandit_pass/bandit26
