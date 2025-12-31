======================================
🎯 OBJECTIVE
======================================
Find the hidden password for bandit31 by analyzing the
bandit30 Git repository. The repository looks empty,
but the password is secretly stored in a Git object.



======================================
🔐 CREDENTIALS PROVIDED
======================================
👤 Username: bandit30  
🔑 Password: (password from previous level)  
🌐 Repo: ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo



======================================
🛠️ METHOD TO SOLVE
======================================
1️⃣ Clone the git repository  
2️⃣ Enter the repo directory  
3️⃣ Check git tags to locate hidden content  
4️⃣ Investigate the secret tag  
5️⃣ Display tag contents to reveal the password  
6️⃣ Use password to log into next level 🎉



======================================
💻 COMMANDS USED
======================================
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
cd repo
git tag
git show-ref --tags
git show secret



======================================
📜 EXPLANATION
======================================
When cloning the repository, it appears empty,
but Git can store data not only in files but also
inside metadata such as tags.

Using:
git tag
we discover a hidden tag called:
secret

Then with:
git show secret
we print the contents of that tag,
and inside it is the password for the next level.

So even though nothing visible exists in the repo,
Git secretly keeps the password stored in tag data.
💡 Important takeaway: Git history and objects
can still hold sensitive information even when not visible!



======================================
📚 CONCEPTS LEARNED
======================================
🧠 Hidden data in Git repositories  
🏷️ Understanding & reading Git tags  
🔎 Using git show & show-ref to extract hidden content  
⚠️ Security Awareness: “Deleting” from Git doesn’t mean gone



======================================
✔️ DONE — PASSWORD FOUND 🎉
======================================
