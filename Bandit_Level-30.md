======================================
🎯 OBJECTIVE (Level 30 → Level 31)
======================================
You are given access to the user bandit30's Git repository.
Your task is to identify and extract the hidden password
for the next level (bandit31). The repository looks empty,
but a secret password is stored somewhere inside Git.



======================================
🔐 CREDENTIALS PROVIDED
======================================
Username: bandit30
Password: (password obtained from Level 29)
Git Repo Access: ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo



======================================
🛠️ METHOD OF SOLVING
======================================
1️⃣ Clone the git repository.
2️⃣ Check what content exists (it appears empty).
3️⃣ Check git tags — hidden information is often stored there.
4️⃣ Identify the secret tag.
5️⃣ Read the contents of the tag.
6️⃣ Extract the password from the tag output.
7️⃣ Use that password for the next level.



======================================
💻 COMMANDS USED
======================================
# Clone the repository
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo

# Enter the repo folder
cd repo

# Check branches (optional)
git branch -a

# List tags
git tag

# View where the secret tag points
git show-ref --tags

# Read the tag content to get password
git show secret



======================================
📜 EXPLANATION
======================================
The repository initially looks empty, which is intentional.
Instead of normal files, the developers hid the password
inside a **Git Tag**. Tags in Git are normally used to mark
versions or releases, but they can also store data.

By listing the tags using `git tag`, we discover a tag named:
secret

Using:
git show secret
we dump the contents of the tag.

The output contains the password required for Bandit31.

This works because Git preserves hidden objects such as
commits, branches, and tags even when files are removed.
So even though the working directory is empty,
the password is still stored inside Git’s metadata.



======================================
📚 CONCEPT LEARNED
======================================
• How to work with remote Git repositories
• How data can exist in Git without files being visible
• Understanding Git tags and how they store data
• Using `git tag`, `git show-ref`, and `git show`
• Security lesson: Sensitive data can remain in Git history
  even if it appears deleted

======================================
✔️ END OF WRITEUP
======================================
