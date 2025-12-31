## Bandit Level 12 → Level 13

### 🎯 Objective
Log in as bandit12 and retrieve the password for the next level from a file that has been repeatedly encoded and compressed in multiple layers.

---

### 🔑 Credentials Provided
Username: bandit12  
Password: Obtained from previous level  

---

### 🔍 Method of Solve
The file `data.txt` contains encoded binary data.  
First, convert it back from hex using `xxd`, then repeatedly use tools such as `gzip`, `bzip2`, and `tar` depending on the detected file type until the actual readable text file is reached.  
Finally, display the file contents to obtain the password.

---

### 🧪 Commands Used (Bash)
- `ls`
- `mkdir /tmp/ctf5 && cp data.txt /tmp/ctf5 && cd /tmp/ctf5`
- `xxd -r data.txt > data`
- `file data`
- `mv data data.gz`
- `gzip -d data.gz`
- `file data`
- `mv data data.bz2`
- `bzip2 -d data.bz2`
- `file data`
- `mv data data.tar`
- `tar -xvf data.tar`
- `file data8.bin`
- `mv data8.bin data.gz`
- `gzip -d data.gz`
- `cat ak`

---

### 🧠 Screenshot (Paste here)
![Bandit Level 12 Screenshot](screenshots/level12.png)

---

### 🔑 Next Level Password
F05dwFsc0cba1H0hl8J2eUks2vdTDwAm

---

### 🧠 Explanation
The `xxd -r` command converts hexadecimal dump back into binary format.  
The `file` command is repeatedly used to identify the type of compressed file each time.  
Based on the output, appropriate tools like `gzip`, `bzip2`, and `tar` are applied repeatedly to unwrap each compression layer.  
Finally, the extracted readable text file reveals the next level password.

---

### 🔐 Concept Learned
- Working with multiple compression formats
- Using `file` to identify unknown file types
- Systematic layered decoding approach
- Importance of temporary writable directory in CTF environments
