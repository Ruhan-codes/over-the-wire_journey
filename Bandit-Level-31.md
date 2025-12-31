## Bandit Level 31 → Level 32


### 🎯 Objective  

- Log in as `bandit31-git`  
- Create the required file  
- Commit the change  
- Push it to the remote repository  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Clone the repository  
- Read the instructions  
- Create `key.txt`  
- Commit the file  
- Push to the remote server  
- Capture the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit31-git  
- **Password:** fb5S2xb7bRyFmAvQYQGegsbvYJqhdNy  


---

### 🔍 Method of Solve  

The remote Git repository requires a specific file to be added.  
Once the file is pushed, the server validates it and returns the next level password.

Steps followed:  
- Clone the repository  
- Read the instructions  
- Create the required file  
- Commit the change  
- Push to the server  


---

### 🧪 Commands Used  

- `git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo`  
- `cd repo`  
- `cat README.md`  
- `echo "May I come in?" > key.txt`  
- `git add key.txt`  
- `git commit -m "Add key.txt file"`  
- `git push origin master`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `git add` | Stages the file for commit |
| `git commit` | Records the change |
| `git push` | Sends the change to the remote server |


---

### 📸 Screenshot Evidence  

**Creating the Required File and Preparing the Commit**  
![Bandit Level 31 – File Creation](screenshots/level31_1.png)

**Pushing the Commit to the Remote Server to Receive the Password**  
![Bandit Level 31 – Push Result](screenshots/level31_2.png)


---

### 🔑 Next Level Password  

```
309RfhaqALVBEZpVb6LYStshZoqoSx5K
```


---

### 🧠 Explanation  

- The repository requires a file named `key.txt`  
- The file must contain the correct text  
- Pushing the commit triggers server-side validation  
- The server returns the password for the next level  


---

### 🔐 Concept Learned  

This level shows how Git repositories can enforce workflows.  
It demonstrates how server-side validation can be triggered by pushing commits.


---

### 🛡️ Security Insight  

Automated Git hooks can be used to enforce security checks.  
They should be carefully designed to avoid unintended data exposure.
