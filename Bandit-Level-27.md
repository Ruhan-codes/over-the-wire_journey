
## Bandit Level 27 → Level 28


### 🎯 Objective  

- Log in as `bandit27-git`  
- Access the private Git repository  
- Read the stored file  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Connect to the Git server over SSH  
- Clone the private repository  
- Enter the repository directory  
- Read the README file  


---

### 🔑 Credentials Provided  

- **Username:** bandit27-git  
- **Password:** upsNc7VZarDX6oZC6GiR6ErwE1M0wGB  


---

### 🔍 Method of Solve  

The password for the next level is stored inside a private Git repository.  
Instead of a normal shell, Git is used to securely access and download the repository.

Steps followed:  
- Clone the repository over SSH  
- Navigate into the repository  
- Read the file containing the password  


---

### 🧪 Commands Used  

- `git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo`  
- `cd repo`  
- `cat README`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `git clone` | Downloads the private repository over SSH |
| `cat README` | Displays the password stored in the repository |


---

### 📸 Screenshot Evidence  

![Bandit Level 27 Screenshot](screenshots/level27.png)


---

### 🔑 Next Level Password  

```
YZ9IpL0sBcCeuG7m9uQFt8ZnpS4HZRcN
```


---

### 🧠 Explanation  

- Git connects to the remote server using SSH  
- The private repository is downloaded locally  
- The README file contains the password for the next level  


---

### 🔐 Concept Learned  

This level demonstrates secure access to private Git repositories.  
It highlights how Git can be used as a secure method of storing and retrieving sensitive data.


---

### 🛡️ Security Insight  

Sensitive data should not be stored in plaintext inside repositories.  
Even private repositories can expose secrets if access is compromised.
