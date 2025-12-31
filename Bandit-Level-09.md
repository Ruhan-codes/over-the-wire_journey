## Bandit Level 09 → Level 10

### 🎯 Objective
Retrieve the password for the next level from `data.txt`.  
The file contains random binary data mixed with human-readable text.  
We must extract readable strings and locate the actual password hidden among them.

---

### 🔑 Credentials Provided
Username: bandit9  
Password: (Password obtained from previous level)

---

### 🔍 Method of Solve
The `data.txt` file is not a normal text file, so reading it directly will not help.
To extract only meaningful readable words from binary data, we use the `strings` command.
Since the password appears next to an equals symbol `=`, we filter the output to only show lines containing `=` using `grep`.

---

### 🧪 Commands Used (Bash)
- `ls -alph`
- `strings data.txt | grep -e "="`

---

### 🧠 Screenshot (Paste your screenshot here)
![Bandit Level 09 Screenshot](screenshots/level09.png)

---

### 🔑 Next Level Password
FGUW5ilLVJrx9XkMYMmlN4MgbpfMiqey

---

### 🧠 Explanation
The `strings` command scans binary files and prints only the readable ASCII text inside.  
By piping it to `grep -e "="`, we narrow down the results to only lines containing `=`, since the challenge hints that the password follows this format.  
From the filtered output, the line containing the complete readable password is identified and used to log into the next level.

---

### 🔐 Concept Learned
- Understanding why binary files cannot be read normally
- Using `strings` to extract readable text from binary files
- Using `grep` with pattern matching to isolate useful information
