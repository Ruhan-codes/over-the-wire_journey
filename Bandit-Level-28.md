
## Bandit Level 28 → Level 29


### 🎯 Objective  

- Log in as `bandit28-git`  
- Access the private Git repository  
- Review the commit history  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Connect to the Git repository over SSH  
- Clone the repository  
- Inspect the commit history  
- Locate the removed password  
- Extract the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit28-git  
- **Password:** YZ9IpL0sBcCeuG7m9uQFt8ZnpS4HZRcN  


---

### 🔍 Method of Solve  

The current version of the repository no longer contains the password.  
However, Git preserves previous versions in its commit history, which can be examined to recover the deleted data.

Steps followed:  
- Clone the private repository  
- View the commit history  
- Inspect earlier file versions  
- Identify the password  


---

### 🧪 Commands Used  

- `git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo`  
- `cd repo`  
- `cat README.md`  
- `git log -p`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `git clone` | Downloads the private repository |
| `git log -p` | Shows commit history with file changes |
| `cat README.md` | Displays the current file version |


---

### 📸 Screenshot Evidence  

![Bandit Level 28 – Repository](screenshots/level28_1.png)

![Bandit Level 28 – Commit History](screenshots/level28_2.png)


---

### 🔑 Next Level Password  

```
4pT1t5DENAyuqnvaYds10e4QLCdjmJ7
```


---

### 🧠 Explanation  

- Git stores all previous versions of files  
- The password was removed from the latest version  
- Viewing earlier commits reveals the original content  
- The original file contains the password for the next level  


---

### 🔐 Concept Learned  

This level demonstrates how deleted data can still exist in Git history.  
It shows why sensitive data should never be committed to version control.


---

### 🛡️ Security Insight  

Secrets must be removed using history rewriting tools.  
Simply deleting them from the latest commit is not sufficient.
