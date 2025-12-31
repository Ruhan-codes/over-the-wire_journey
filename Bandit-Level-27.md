## Bandit Level 27 → Level 28

### 🎯 Objective
Access the Bandit Git repository, retrieve its contents, and obtain the password for the next level.

### 🔑 Credentials Provided
Username: bandit27  
Password: (from previous level)  
Repository Location: ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo  

### 🔍 Method of Solve
This level provides access to a remote Git repository that contains the next level password.  
We need to clone the repository using Git over SSH, navigate inside it, and read the README file.

### 🧪 Commands Used
##### Clone the remote repository
git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo

##### Enter the cloned repository
cd repo

##### Read the README file
cat README

### 🔑 Next Level Password
Yz91pL0sBCceuG7m9uQFt8ZNpS4HZRcN

### 🧠 Explanation
The repository contains only a README file. This file directly stores the Bandit28 password.  
By cloning with SSH authentication, we access the repo contents and extract the password.

### 🔐 Concept Learned
This level teaches:
- Using Git over SSH
- Accessing remote repositories securely
- Reading repository contents
