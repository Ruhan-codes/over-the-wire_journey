## Bandit Level 20 → Level 21

### 🎯 Objective
Use the `suconnect` SUID binary to send the current level password to a listening localhost port. If correct, receive the password for the next level.

---

### 🔑 Credentials Provided
Username: bandit20  
Password: 0qXahG8Zj0VMN9Ghs7iOWsCfZyXOUbY0  

---

### 🔍 Method of Solve
1. Choose a port number (example: 5000).
2. Start a Netcat listener on that port.
3. Run the `suconnect` program with the same port.
4. When the connection happens, `suconnect` sends the password, verifies it, and returns the next level password.

---

### 🧪 Commands Used
nc -lvp 5000
./suconnect 5000

---

### 📸 Screenshot
(Place Screenshot Here)

---

### 🔑 Next Level Password
EeoULMCra2q0qDsKyj5l6lDX7s1CpBuOBt

---

### 🧠 Explanation
- `nc -lvp 5000` opens a listening TCP port.
- `./suconnect 5000` is a SUID-root helper tool that connects to that port and sends the current password.
- Once validated, Bandit21 password is returned through the connection.

---

### 🔐 Concept Learned
- Working with SUID binaries
- TCP communication using Netcat
- Local privilege and password transfer concepts
