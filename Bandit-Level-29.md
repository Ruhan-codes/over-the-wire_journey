
## Bandit Level 29 → Level 30


### 🎯 Objective  

- Log in as `bandit29-git`  
- Explore all branches of the Git repository  
- Identify the branch containing the password  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Connect to the Git repository over SSH  
- Clone the repository  
- List available branches  
- Switch to the `dev` branch  
- Review the commit history  
- Extract the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit29-git  
- **Password:** 4pT1t5DENAyuqnvaYds10e4QLCdjmJ7  


---

### 🔍 Method of Solve  

The password is not stored in the main branch of the repository.  
It exists in a different branch named `dev`, which contains earlier versions of the files.

Steps followed:  
- Clone the private repository  
- List all branches  
- Switch to the `dev` branch  
- Review commit history  
- Find the password  


---

### 🧪 Commands Used  

- `git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo`  
- `cd repo`  
- `cat README.md`  
- `git branch`  
- `git branch -a`  
- `git checkout dev`  
- `git log -p`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `git branch -a` | Lists all branches including remote ones |
| `git checkout dev` | Switches to the development branch |
| `git log -p` | Displays commit history and file changes |


---

### 📸 Screenshot Evidence  

**Cloning the Repository and Checking Available Branches**  
![Bandit Level 29 – Repository](screenshots/level29_1.png)

**Viewing the Commit History in the Dev Branch to Reveal the Password**  
![Bandit Level 29 – Dev Branch Commit](screenshots/level29_2.png)


---

### 🔑 Next Level Password  

```
qp3oEX3VLz5MDG1n91YowTv4Q8I7CDZL
```


---

### 🧠 Explanation  

- The repository contains multiple branches  
- The `dev` branch includes earlier versions of files  
- The commit history reveals the password  
- The password is extracted from a previous commit  


---

### 🔐 Concept Learned  

This level shows how data can exist across different Git branches.  
It highlights the need to inspect all branches when searching for sensitive information.


---

### 🛡️ Security Insight  

Secrets stored in development branches can still be exposed.  
All branches must be reviewed and cleaned to protect sensitive data.
