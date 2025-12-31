## Bandit Level 28 → Level 29

### 🎯 Objective
Access the git repository for bandit28, investigate its commit history, and recover the password for bandit29.

### 🔑 Credentials Provided
Username: bandit28  
Password: (from previous level)

### 🔍 Method of Solve
After cloning the remote git repository, the README file appears to have the password removed.  
To retrieve earlier versions of the README, inspect the git commit history and view differences between commits to reveal the password before it was redacted.

### 🧪 Commands Used
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo  
cd repo  
ls  
cat README.md  
git log -p  

### 🧠 Explanation
1. The repository is cloned using SSH with the bandit28 credentials.  
2. Opening README.md shows that the password field is hidden.  
3. `git log -p` is used to display commit history along with patches showing what changed in each version.  
4. Scanning through earlier commits reveals the password before it was censored.

### 📌 Password to the Next Level
4pt1t5DEnaYuqnqvaYsl0e4QLcdjm7J

### 🔐 Concept Learned
This level teaches:
- Basic Git usage in security contexts  
- How sensitive information can still be retrieved from commit history  
- Importance of cleaning repository history to prevent leaks
