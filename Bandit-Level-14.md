## Bandit Level 14 → Level 15

### 🎯 Objective
Use the password from the previous level to authenticate to a local service listening on port 30000 and retrieve the password for the next level.

---

### 🔑 Credentials Provided
Username: bandit14  
Password: mU4V4VeTyJk8RO0f1qqmcBPaLh71DCpV5

---

### 🔍 Method of Solve
There is a service running on the local machine at port 30000 which validates the password of bandit14.  
By connecting to this port and providing the correct password, the service returns the password for the next level.

---

### 🧪 Commands Used (Bash)
- `nc localhost 30000`
- Enter the bandit14 password when prompted

---

### 📷 Screenshot (Paste Here)
![Bandit Level 14 Screenshot](screenshots/level14.png)

---

### 🔑 Next Level Password
8xCjnmgoKBGhLHfFAZ1GEl5Tmu4M2tKJQ0

---

### 🧠 Explanation
The `nc` (netcat) command is used to connect to services running on specific ports.  
By connecting to `localhost` at port `30000`, we interact with a validation service.  
When the correct password is entered, the service verifies it and prints the password for the next level.

---

### 🔐 Concept Learned
- Using Netcat to communicate with network services
- Understanding local port-based authentication services in CTF environments
