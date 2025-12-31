
## Bandit Level 24 → Level 25


### 🎯 Objective  

- Log in as `bandit24`  
- Connect to the local authentication service  
- Brute-force the 4-digit PIN  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Login as `bandit24`  
- Write a Python brute-force script  
- Try all PINs from `0000` to `9999`  
- Capture the correct response  
- Extract the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit24  
- **Password:** gb8KRRcsshuzXi0tUuR6ypOFjiZbf3G8  


---

### 🔍 Method of Solve  

A service running on port `30002` requires the current password and a 4-digit PIN.  
Because the PIN space is small, it can be brute-forced by testing every possible combination.

Steps followed:  
- Create a Python script  
- Connect to the service repeatedly  
- Send each PIN with the password  
- Detect the correct response  


---

### 🧪 Commands Used  

- `cd /tmp/ak`  
- `ls -la`  
- `nano ...ak.py`  
- `python3 ...ak.py`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `nano ...ak.py` | Creates the brute-force Python script |
| `python3 ...ak.py` | Executes the brute-force attack |


---

### 📸 Screenshot Evidence  

**Step 1 – Creating the Python Brute-Force Script**  
![Bandit Level 24 – Python Script](screenshots/level24_1.png)

**Step 2 – Successful PIN Brute-Force and Password Retrieval**  
![Bandit Level 24 – Password Found](screenshots/level24_2.png)


---

### 🔑 Next Level Password  

```
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```


---

### 🧠 Explanation  

- The script connects to the service on port `30002`  
- Each 4-digit PIN is sent with the current password  
- When the correct PIN is found, the service returns the password  
- The script captures and prints the result  


---

### 🔐 Concept Learned  

This level demonstrates how small key spaces can be brute-forced.  
It highlights the risks of weak authentication mechanisms.


---

### 🛡️ Security Insight  

Services must implement rate-limiting and lockouts.  
Without these, brute-force attacks can easily compromise accounts.
