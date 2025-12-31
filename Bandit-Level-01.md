## Bandit Level 01 → Level 02

### 🎯 Objective  
Log in to the Bandit game using the provided credentials and retrieve the password for the next level from a file named `-` in the home directory.

---

### 🔑 Credentials Provided  
Username: bandit1  
Password: Obtained from previous level  

---

### 🔍 Method of Solve  
The password is stored inside a file named `-`. However, this filename is interpreted as an option by many Linux commands. Therefore, instead of using `cat -`, we must specify the file path explicitly using `./-` to indicate it is a file in the current directory.

---

### 🧪 Commands Used
- ls  
- cat ./-  

![Bandit Level 01 Screenshot](screenshots/level01.png)

---

### 🧠 Explanation  
The `ls` command is used to list files in the current directory, which shows that a file named `-` exists.  
Normally, `cat -` means reading input from the keyboard, not a file.  
By using `cat ./-`, we clearly tell the system that `-` is a filename located in the current directory.  
Executing this command displays the contents of the file, which contains the password for the next level.

---

### 🔐 Concept Learned  
This level teaches how special filenames like `-` can behave differently in Linux.  
It also demonstrates the importance of using relative paths like `./filename` to correctly access files with special names.
