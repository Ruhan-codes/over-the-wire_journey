
## Bandit Level 20 → Level 21


### 🎯 Objective  

- Log in as `bandit20`  
- Run the set-UID network program  
- Capture the transmitted password  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit20`  
- Start a Netcat listener  
- Run `suconnect` to send the password  
- Capture the output  


---

### 🔑 Credentials Provided  

- **Username:** bandit20  
- **Password:** oqXahG8ZjOVMN9Ghs710WsCfZyXOUbY0  


---

### 🔍 Method of Solve  

A set-UID program named `suconnect` runs with `bandit21` privileges.  
It sends the next level password to a service listening on a specified port.

Steps followed:  
- Start a Netcat listener on a chosen port  
- Run `suconnect` to connect to that port  
- Capture the transmitted password  


---

### 🧪 Commands Used  

- `nc -lvp 5000`  
- `./suconnect 5000`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `nc -lvp 5000` | Starts a Netcat listener on port 5000 |
| `./suconnect 5000` | Sends the password to the specified port |


---

### 📸 Screenshot Evidence  

![Bandit Level 20 Screenshot](screenshots/level20.png)


---

### 🔑 Next Level Password  

```
Ee0ULMCrq2q0dSKYj561DX7s1CpBuOBt
```


---

### 🧠 Explanation  

- Netcat waits for incoming connections on port 5000  
- The `suconnect` program connects to that port  
- The program sends the next level password  
- The password is displayed in the Netcat listener  


---

### 🔐 Concept Learned  

This level demonstrates how privileged network programs can transmit sensitive data.  
It highlights how listening on the correct port can capture that information.


---

### 🛡️ Security Insight  

Network services running with elevated privileges must be secured.  
Otherwise, attackers can intercept sensitive data by listening on exposed ports.
