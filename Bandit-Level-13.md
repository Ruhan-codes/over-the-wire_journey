## Bandit Level 13 → Level 14

### 🎯 Objective
Log in to the Bandit server using a private SSH key instead of a password and retrieve the password for the next level from the `/etc/bandit_pass` directory.

---

### 🔑 Credentials Provided
Username: bandit13  
Authentication: Private SSH Key (`sshkey.private`)

---

### 🔍 Method of Solve
The private key required for authentication is stored on the Bandit13 account.  
First, securely copy the private key to the local machine.  
Then set the correct permissions so it can be used.  
Finally, log in using the key and read the password file of bandit14 stored in `/etc/bandit_pass`.

---

### 🧪 Commands Used (Bash)
- `scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .`
- `chmod 600 sshkey.private`
- `ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`
- `cd /etc/bandit_pass`
- `cat bandit14`

---

### 📷 Screenshot (Paste here)
![Bandit Level 13 Screenshot](screenshots/level13.png)

---

### 🔑 Next Level Password
mU4V4veuTvqy7jR8RooofIqomcBPAln17DCpV5

---

### 🧠 Explanation
`scp` is used to securely download the private SSH key from the Bandit13 home directory.  
`chmod 600` ensures the key has the correct permissions, otherwise SSH refuses to use it.  
Using the `ssh -i` option allows login without a password.  
Inside `/etc/bandit_pass`, each level's password is stored in a file named after the user, so reading `bandit14` reveals the next password.

---

### 🔐 Concept Learned
- Secure Copy (SCP) usage
- SSH authentication using private keys
- Linux file permissions importance in SSH security
- Accessing protected system directories
