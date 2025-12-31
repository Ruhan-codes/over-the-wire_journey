## Bandit Level 25 → Level 26

### 🎯 Objective
SSH into bandit26 using the private SSH key, bypass the restricted shell, and retrieve the password for bandit27.

### 🔑 Credentials Provided
Username: bandit26  
Authentication: Private SSH Key (bandit26.sshkey)  
Port: 2220  

### 🔍 Method of Solve
1. Retrieve the SSH private key from bandit25.
2. Copy the key to your local machine using SCP.
3. Fix key permissions or SSH will refuse to use it.
4. SSH into bandit26 using the key.
5. You are dropped into a restricted shell that only allows `more`.
6. Use `v` inside more to escape into **vim editor**.
7. From vim, open a shell using `:shell`.
8. Access the password file and retrieve the bandit27 password.

### 🧪 Commands Used
##### Copy SSH key from server to local machine
scp -P 2220 bandit25@bandit.labs.overthewire.org:/home/bandit25/bandit26.sshkey .

##### Fix key permissions
chmod 600 bandit26.sshkey

##### SSH into bandit26
ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220

##### Inside restricted shell use viewer trick
# press "v" to open vim  
:shell

##### Read next level password
cat /etc/bandit_pass/bandit26

##### Bandit27 Password
s0773xxkkk0MXfdq0fPRVY9L3jBU0gCZ

### 🧠 Explanation
The SSH key grants access, but instead of a normal shell, Bandit26 drops us into a restricted environment using `more`, preventing normal command execution.  
However, `more` allows entering **vim**, and vim lets us spawn a full shell using `:shell`.  
Once we gain full shell access, we can simply read the password stored in `/etc/bandit_pass/bandit26`.

### 🔐 Concept Learned
This level demonstrates:
- SSH key authentication
- File permission handling for SSH keys
- Restricted shells and escape techniques
- Using vim to break restricted environments
- Privilege controlled password storage in Linux
