## Bandit Level 07 → Level 08

### 🎯 Objective
Find the password for the next level. The password is stored in a file named `data.txt`, but it is hidden among a large amount of human-readable and binary content. The correct password is located next to the word "millionth".

---

### 🔑 Credentials Provided
Username: bandit7  
Password: (Password obtained from previous level)

---

### 🔍 Method of Solve
The file `data.txt` is extremely large (around 4MB) and contains many unreadable characters.  
We need to extract only human-readable strings and then locate the line that contains the keyword "millionth", because the challenge instructions say that the password is the “millionth” line.

To do this:
1. Use `strings` to extract readable ASCII text from the file
2. Pipe the output to `grep` to search for the word "millionth"
3. Read the corresponding password printed next to it

---

### 🧪 Commands Used (Bash)
- `ls -alph`
- `strings data.txt | grep "millionth"`

---

### 🧠 Screenshot (Paste your screenshot here)
![Bandit Level 07 Screenshot](screenshots/level07.png)

---

### 🔑 Next Level Password
dfwvzFQi4mlU0wNfbFOe9ROwSkmLG7eEc

---

### 🧠 Explanation
The `strings` command extracts only printable ASCII characters from binary or messy files, making it easier to locate meaningful data.
We then pipe (`|`) the output to `grep`, which filters and displays only the line containing the word “millionth”.  
The password is printed on the same line, immediately after the keyword.

---

### 🔐 Concept Learned
- How to extract readable text from large or binary files using `strings`
- Using `grep` to search within filtered output
- Understanding how piping helps combine multiple commands to solve challenges efficiently
