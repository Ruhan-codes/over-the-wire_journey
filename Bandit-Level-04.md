## Bandit Level 04 → Level 05

### 🎯 Objective  
Log in to the Bandit game as bandit4 and retrieve the password for the next level from one of the files located in the `inhere` directory.

---

### 🔑 Credentials Provided  
Username: bandit4  
Password: Obtained from previous level  

---

### 🔍 Method of Solve  
The password is stored in one of several files inside the `inhere` directory.  
Most of the files contain binary data, but only one contains readable ASCII text.  
Therefore, the task is to identify which file contains human-readable text and then read its content.

---

### 🧪 Commands Used  
- ls  
- cd inhere  
- ls -alph  
- find . -type f | xargs file  
- cat ./-file07  

![Bandit Level 04 Screenshot](screenshots/level04.png)

---

### 🔑 Next Level Password  
tKOq9UJONZOOEO5YpwTWB1FB8j8LxXGUQw

---

### 🧠 Explanation  
The `ls` command lists available directories and reveals the `inhere` directory.  
Using `cd inhere` moves into the directory containing multiple files.  
The `ls -alph` command lists all files, including those with special naming formats.  
Since the correct file is the one containing readable text, the `find . -type f | xargs file` command is used to identify the type of data each file contains.  
Among them, `-file07` is detected as an ASCII text file.  
Finally, running `cat ./-file07` prints the contents of the file, revealing the password for the next level.

---

### 🔐 Concept Learned  
This level demonstrates how to analyze multiple files efficiently in Linux.  
It teaches the use of the `file` command to determine file types and reinforces handling files with special names using relative paths like `./filename`.
