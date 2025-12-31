## Bandit Level 31 → Level 32

### 🎯 Objective  
Gain access to the next level by pushing a specific file (`key.txt`) with the required content into the remote Git repository on the **master** branch.

---

### 🔑 Credentials Provided  
- **Username:** bandit31  
- **Password:** (from previous level)

---

### 🔍 Method of Solve  
1. Clone the Bandit Git repository using SSH.
2. Read the README to understand the goal.
3. Create the required file `key.txt` with the given content.
4. Add, commit, and push the file to the repository.
5. The server returns the password in the push response, even if the push is rejected.

---

### 🧪 Commands Used
```bash
git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo
cat README.md
echo "May I come in?" > key.txt
git add key.txt -f
git commit -m "Add key.txt file"
git push origin master
```

---

### 🧠 Explanation  
The README states that you must **push a file to the repository**.  
You create `key.txt` with the exact content required.  
Even though pushing is *rejected by security hooks*, the server prints a hidden success message containing the next password during the push output.  
So we only need to trigger the push — the response reveals the password.

---

### 📸 Screenshot Placement  
(Place your screenshot here showing the push output and password)level31.png

---

### 🔐 Next Level Password  
`3093NHqvalVBEPZvYDb6LYStshZoqoSz5K`

---

### 🧠 Concept Learned  
- Understanding Git remote hooks  
- Forced file staging  
- Working with SSH Git authentication  
- Extracting useful data from server responses  

