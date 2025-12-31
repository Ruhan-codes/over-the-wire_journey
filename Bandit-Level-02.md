## Bandit Level 02 → Level 03

### 🎯 Objective  
Log in to the Bandit game as bandit2 and retrieve the password for the next level from a file whose name contains spaces.

---

### 🔑 Credentials Provided  
Username: bandit2  
Password: Obtained from previous level  

---

### 🔍 Method of Solve  
The password for the next level is stored inside a file named `spaces in this filename`.  
Since spaces break filenames into separate arguments in Linux, the filename must either be quoted or escaped to read it correctly.

---

### 🧪 Commands Used  
- ls  
- cat "spaces in this filename"  
  OR  
- cat spaces\ in\ this\ filename  

![Bandit Level 02 Screenshot](screenshots/level02.png)

---

### 🔑 Next Level Password  
MNk8KNHJ3uSio14PRUeODFpqfxfLPLSmx

---

### 🧠 Explanation  
The `ls` command lists all files and reveals a file named `spaces in this filename`.  
In Linux, spaces separate arguments, so typing `cat spaces in this filename` would be interpreted as multiple inputs instead of a single filename.  
To correctly reference it, either quotation marks `" "` are used or each space is escaped using a backslash `\`.  
Running the correct command displays the file contents, revealing the password for the next level.

---

### 🔐 Concept Learned  
This level teaches how to handle filenames containing spaces in Linux.  
It demonstrates the use of quotes and escape characters to correctly access such files.
