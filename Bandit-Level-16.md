## Bandit Level 16 → Level 17

### 🎯 Objective
Log in as bandit16 and obtain the password for bandit17 by discovering the correct SSL-enabled port running a service that returns a private SSH key.

---

### 🔑 Credentials Provided
- **Username:** bandit16
- **Password:** kSkVUpMQ7BIbYCMl4GBPvCVI1BFwRyo0Dx

---

### 🔍 Method of Solve
We know multiple services are running between **ports 31000–32000** on localhost.
We must:
1) Scan to find open ports
2) Identify which one supports SSL
3) Connect to the correct service
4) Submit the password
5) Receive an SSH private key for the next level

We then use this private key to login as **bandit17**.

---

### 🧪 Commands Used
- `nmap -sV -p 31000-32000 localhost`
  Scans local ports and detects SSL services

- `ncat --ssl localhost <port>`
  Connect to discovered SSL ports and test

- When the correct port is found, it returns an RSA Private Key

- Save the key:
  `nano key17`
  (paste the key)

- Secure the key:
  `chmod 600 key17`

- Login to next level:
  `ssh -i key17 bandit17@bandit.labs.overthewire.org -p 2220`

---

### 🖼 Screenshot
![Bandit Level 16 Screenshot](screenshots/level16.png)

---

### 🔑 Next Level Key Output
You receive a full **RSA PRIVATE KEY** which is used to log into bandit17.

---

### 🧠 Explanation
Multiple network services were running locally.  
We scanned all ports from **31000–32000** to identify which ones were active.  
Among them, only one SSL-enabled service correctly verified our password and returned an SSH private key.  
This key acts as authentication to log into the next level instead of a password.

---

### 🔐 Concept Learned
- Using **nmap** for service discovery
- Identifying SSL-enabled services
- Secure communication using **ncat with SSL**
- Working with **SSH private keys**
- Proper key permissions using `chmod 600`
- Logging in with `ssh -i keyfile user@host`
