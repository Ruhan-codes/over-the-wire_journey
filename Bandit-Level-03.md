## Bandit Level 03 → Level 04

### 🎯 Objective  
Log in to the Bandit game as bandit3 and retrieve the password for the next level from a hidden file located inside a directory.

---

### 🔑 Credentials Provided  
Username: bandit3  
Password: Obtained from previous level  

---

### 🔍 Method of Solve  
The password is stored inside a hidden file located in the directory named `inhere`.  
Hidden files do not appear with normal listing, so an advanced listing command must be used to view them.

---

### 🧪 Commands Used  
- ls  
- cd inhere  
- ls -alph  
- cat ...Hiding-From-You  

![Bandit Level 03 Screenshot](screenshots/level03.png)

---

### 🔑 Next Level Password  
2WmrDFRmJiTq3IPxneAAMGhap0pFhF3NJ

---

### 🧠 Explanation  
The `ls` command lists the available directories and shows a directory named `inhere`.  
Using `cd inhere` moves into that directory.  
The `ls -alph` command lists all files including hidden files (files that start with `.`).  
This reveals a hidden file named `...Hiding-From-You`.  
Finally, using `cat ...Hiding-From-You` displays the contents of the hidden file, which contains the password for the next level.

---

### 🔐 Concept Learned  
This level teaches how to locate and read hidden files in Linux.  
It highlights the use of `ls -a` to reveal hidden files and demonstrates directory navigation combined with file reading commands.
