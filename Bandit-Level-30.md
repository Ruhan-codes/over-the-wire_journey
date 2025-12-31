## Bandit Level 30 → Level 31


### 🎯 Objective  

- Log in as `bandit30-git`  
- Explore Git references  
- Identify the hidden tag  
- Retrieve the password for the next level  


---

### 🧭 Quick Action Summary  

- Clone the private repository  
- List all Git tags  
- Inspect the hidden tag  
- Extract the password  


---

### 🔑 Credentials Provided  

- **Username:** bandit30-git  
- **Password:** qp3oEX3VLz5MDG1n91YowTv4Q8I7CDZL  


---

### 🔍 Method of Solve  

The password is not stored in the repository files or branches.  
Instead, it is hidden inside a Git tag, which must be inspected to retrieve the data.

Steps followed:  
- Clone the repository  
- List available tags  
- View the tag content  
- Read the password  


---

### 🧪 Commands Used  

- `git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo`  
- `cd repo`  
- `cat README.md`  
- `git tag`  
- `git show-ref --tags`  
- `git show secret`  


---

### 🧩 Command Purpose  

| Command | Purpose |
|--------|--------|
| `git tag` | Lists all tags |
| `git show secret` | Displays the data stored inside the tag |


---

### 📸 Screenshot Evidence  

**Cloning the Repository and Checking Files**  
![Bandit Level 30 – Repository](screenshots/level30_1.png)

**Viewing the Hidden Git Tag That Contains the Password**  
![Bandit Level 30 – Git Tag](screenshots/level30_2.png)


---

### 🔑 Next Level Password  

```
fb5S2xb7bRyFmAvQYQGegsbvYJqhdNy
```


---

### 🧠 Explanation  

- The repository files do not contain the password  
- A hidden Git tag stores the password  
- Inspecting the tag reveals the next level credentials  


---

### 🔐 Concept Learned  

This level shows that Git tags can contain hidden information.  
It highlights the importance of inspecting all Git references during security reviews.


---

### 🛡️ Security Insight  

Sensitive data should never be stored in Git tags.  
Tags are easily accessible and can expose confidential information.
