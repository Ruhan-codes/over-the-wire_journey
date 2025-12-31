## Bandit Level 06 → Level 07

### 🎯 Objective
Find the password for the next level. The password is stored on the server in a file owned by user bandit7, group bandit6, and with a size of 33 bytes.

---

### 🔑 Credentials Provided
Username: bandit6  
Password: (Password obtained from previous level)

---

### 🔍 Method of Solve
We must search the system for a file that:
1. Is owned by user bandit7  
2. Is owned by group bandit6  
3. Has a file size of exactly 33 bytes  

Once found, we read the file to retrieve the password.

---

### 🧪 Commands Used (Bash)
- `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`
- `cat /var/lib/dpkg/info/bandit7.password`

---

### 🧠 Screenshot (Paste your screenshot here)
![Bandit Level 06 Screenshot](screenshots/level06.png)

---

### 🔑 Next Level Password
morbNTDKWS6jIlUc0ym0dMaLn0LFVAaj

---

### 🧠 Explanation
The `find` command searches the filesystem for files that match specific conditions.  
- `-type f` ensures we only search for regular files.  
- `-user bandit7` limits results to files owned by bandit7.  
- `-group bandit6` ensures the group ownership matches bandit6.  
- `-size 33c` filters files exactly 33 bytes in size.  
- `2>/dev/null` hides permission denied errors so output is clean.

Once the correct file `/var/lib/dpkg/info/bandit7.password` was found, using `cat` displayed the password for the next level.

---

### 🔐 Concept Learned
- Using the `find` command with permissions and ownership filters  
- Understanding file search based on size, user, and group  
- Redirecting errors to `/dev/null` for cleaner terminal output
