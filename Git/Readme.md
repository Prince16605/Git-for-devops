# 🚀 Git & GitHub 

A complete practical guide to learn **Git and GitHub**, including installation, repository creation, staging, commits, push/pull, clone, fork, reset, stash, tags, `.gitignore`, branches, and Git workflow.

---

## 📌 Table of Contents

1. What is Git?
2. Git vs GitHub
3. Install Git
4. Configure Git Username & Email
5. Create a Git Repository
6. Git 3-Stage Workflow
7. Git Status
8. Git Add – Staging Area
9. Git Commit
10. Git Push
11. Git Pull
12. Git Clone
13. Git Fork
14. `.gitignore`
15. Git Reset
16. Git Revert
17. Git Log
18. Git Tag
19. Git Stash
20. Git Branch
21. Git Merge
22. Remote Repository Commands
23. Useful Git Commands
24. Complete Git Workflow
25. Git Cheat Sheet

---

# 1. 🔥 What is Git?

**Git** is a distributed version control system used to track changes in files and source code.

Git helps developers to:

* Track file changes
* Maintain different versions
* Work with multiple developers
* Restore previous versions
* Create branches
* Merge changes
* Upload projects to GitHub

Example:

```bash
git status
git add .
git commit -m "Initial commit"
git push
```

---

# 2. 🆚 Git vs GitHub

| Git                       | GitHub                         |
| ------------------------- | ------------------------------ |
| Version Control System    | Cloud-based Git platform       |
| Runs on local computer    | Runs on the internet           |
| Tracks code changes       | Stores Git repositories online |
| Created by Linus Torvalds | Owned by Microsoft             |
| Can work without internet | Usually requires internet      |

---

# 3. 💻 Install Git

## Windows

Download Git from:

https://git-scm.com/

Check installation:

```bash
git --version
```

Example:

```text
git version 2.x.x
```

## Linux

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install git
```

### RHEL / CentOS / Amazon Linux

```bash
sudo yum install git
```

Check:

```bash
git --version
```

---

# 4. 👤 Configure Git Username & Email

Set username:

```bash
git config --global user.name "Your Username"
```

Set email:

```bash
git config --global user.email "your@email.com"
```

Example:

```bash
git config --global user.name "Prince Vaghasiya"
git config --global user.email "your@email.com"
```

Check configuration:

```bash
git config --list
```

Check username:

```bash
git config user.name
```

Check email:

```bash
git config user.email
```

### Local Repository Configuration

If you want configuration only for the current repository:

```bash
git config user.name "Prince Vaghasiya"
git config user.email "your@email.com"
```

---

# 5. 📁 Create a Git Repository

Create a project directory:

```bash
mkdir my-project
```

Enter the directory:

```bash
cd my-project
```

Create a file:

```bash
touch index.html
```

Initialize Git:

```bash
git init
```

Output:

```text
Initialized empty Git repository
```

Git creates a hidden `.git` directory.

Check:

```bash
ls -la
```

---

# 6. 🔄 Git 3-Stage Workflow

Git mainly works with three important areas:

```text
                  🔄 GIT 3-STAGE WORKFLOW

┌────────────────────────────┐
│     📝 WORKING DIRECTORY   │
│                            │
│  Create / Modify files     │
│                            │
└──────────────┬─────────────┘
               │
               │ git add
               ▼
┌────────────────────────────┐
│       📦 STAGING AREA      │
│                            │
│  Files selected for the    │
│  next commit               │
│                            │
└──────────────┬─────────────┘
               │
               │ git commit
               ▼
┌────────────────────────────┐
│     🗃️ LOCAL REPOSITORY    │
│                            │
│  Committed snapshots       │
│  stored by Git             │
│                            │
└──────────────┬─────────────┘
               │
               │ git push
               ▼
┌────────────────────────────┐
│     ☁️ GITHUB / REMOTE     │
│        REPOSITORY          │
└────────────────────────────┘
```

## 📌 Simple Flow

```text
Working Directory
       │
       │ git add
       ▼
Staging Area
       │
       │ git commit
       ▼
Local Repository
       │
       │ git push
       ▼
GitHub
```

### 1️⃣ Working Directory

This is where you create and modify files.

Example:

```text
index.html
style.css
script.js
```

### 2️⃣ Staging Area

Files selected for the next commit are placed here.

Command:

```bash
git add filename
```

or:

```bash
git add .
```

### 3️⃣ Local Repository

Committed changes are stored in the local Git repository.

Command:

```bash
git commit -m "message"
```

### 4️⃣ Remote Repository

The repository stored on GitHub.

Command:

```bash
git push
```

---

# 7. 🔍 Git Status

`git status` shows the current condition of your repository.

```bash
git status
```

It can show:

* Untracked files
* Modified files
* Staged files
* Current branch

Example:

```text
Untracked files:
    index.html
```

---

# 8. ➕ Git Add – Staging Area

Add one file:

```bash
git add index.html
```

Add multiple files:

```bash
git add file1.txt file2.txt
```

Add all files:

```bash
git add .
```

Another command:

```bash
git add -A
```

Check:

```bash
git status
```

Now the files are in the **Staging Area**.

---

# 9. 💾 Git Commit

Commit staged changes:

```bash
git commit -m "Initial commit"
```

Example:

```bash
git commit -m "Added index page"
```

A commit creates a snapshot of the staged changes in the local repository.

---

# 10. ☁️ Git Push

Connect local repository with GitHub:

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

Check remote:

```bash
git remote -v
```

Rename branch to `main`:

```bash
git branch -M main
```

Push:

```bash
git push -u origin main
```

After first push:

```bash
git push
```

### Complete First Push

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

---

# 11. 📥 Git Pull

`git pull` downloads changes from the remote repository and integrates them into the current branch.

```bash
git pull
```

Or:

```bash
git pull origin main
```

---

# 12. 📥 Git Clone

`git clone` creates a local copy of a remote repository.

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

Example:

```bash
git clone https://github.com/Prince16605/my-project.git
```

Clone into a specific directory:

```bash
git clone https://github.com/USERNAME/REPOSITORY.git my-project
```

Then:

```bash
cd my-project
git status
```

---

# 13. 🍴 Git Fork

**Fork** is mainly a GitHub feature, not a Git command.

A fork creates your own copy of another user's GitHub repository under your GitHub account.

### Fork Workflow

```text
Original Repository
        │
        │ Fork
        ▼
Your GitHub Repository
        │
        │ git clone
        ▼
Local Computer
        │
        │ Modify
        ▼
git add
        │
        ▼
git commit
        │
        ▼
git push
        │
        ▼
Pull Request
        │
        ▼
Original Repository
```

There is no:

```bash
git fork
```

command.

You use the **Fork** button on GitHub.

---

# 14. 🚫 `.gitignore`

`.gitignore` tells Git which files/directories should not be tracked.

Create:

```bash
touch .gitignore
```

Example:

```text
node_modules/
.env
*.log
*.tmp
password.txt
```

Example `.gitignore`:

```text
# Environment variables
.env

# Logs
*.log

# Temporary files
*.tmp

# Node modules
node_modules/

# Python cache
__pycache__/

# IDE files
.vscode/
```

Check ignored files:

```bash
git status --ignored
```

### ⚠️ Never Commit

* Passwords
* API keys
* AWS access keys
* `.env` files
* Private keys

---

# 15. 🔄 Git Reset

`git reset` is used to move `HEAD` and/or change the staging state.

## Git Reset Diagram

```text
                       🔄 GIT RESET

                    ┌──────────────┐
                    │     HEAD     │
                    │      ↓       │
                    │   Commit C3  │
                    └──────┬───────┘
                           │
                           │ git reset HEAD~1
                           ▼
                    ┌──────────────┐
                    │   Commit C2  │
                    │      ↑       │
                    │     HEAD     │
                    └──────────────┘
```

---

## 🟢 Git Reset --soft

```bash
git reset --soft HEAD~1
```

### What happens?

* Latest commit is removed from branch history.
* Changes remain in the **Staging Area**.
* Files are not deleted.

```text
        Commit C3
            │
            │ --soft
            ▼
        ❌ Commit removed
            │
            ▼
     📦 Staging Area
            │
            ▼
     Changes remain staged
```

### Flow

```text
Commit
  ↓
❌ Removed
  ↓
Staging Area
  ↓
Changes remain staged
```

---

## 🟡 Git Reset --mixed

```bash
git reset --mixed HEAD~1
```

`--mixed` is the default reset mode.

You can also use:

```bash
git reset HEAD~1
```

### What happens?

* Latest commit is removed.
* Changes are removed from staging.
* Files remain in the **Working Directory**.
* Files are not deleted.

```text
        Commit C3
            │
            │ --mixed
            ▼
        ❌ Commit removed
            │
            ▼
     📝 Working Directory
            │
            ▼
      Changes become
         unstaged
```

---

## 🔴 Git Reset --hard

```bash
git reset --hard HEAD~1
```

### What happens?

* Latest commit is removed.
* Staging changes are removed.
* Working directory changes are also discarded.

```text
        Commit C3
            │
            │ --hard
            ▼
        ❌ Commit removed
            │
            ▼
       🗑️ Changes
       discarded
```

⚠️ **Be careful with `--hard`.**
It can permanently discard uncommitted changes.

---

## 📊 Reset Comparison

| Reset Type | Commit  | Staging               | Working Directory |
| ---------- | ------- | --------------------- | ----------------- |
| `--soft`   | Removed | Changes remain staged | Changes remain    |
| `--mixed`  | Removed | Changes unstaged      | Changes remain    |
| `--hard`   | Removed | Changes removed       | Changes discarded |

### Easy Way to Remember

```text
--soft
Commit ❌
Staging ✅
Files ✅

--mixed
Commit ❌
Staging ❌
Files ✅

--hard
Commit ❌
Staging ❌
Files ❌
```

---

## Remove File from Staging

If you accidentally added a file:

```bash
git restore --staged filename
```

Example:

```bash
git restore --staged index.html
```

Older command:

```bash
git reset HEAD index.html
```

This does **not delete the file**.

```text
Staging Area
      │
      │ git restore --staged
      ▼
Working Directory
```

---

# 16. ↩️ Git Revert

`git revert` creates a new commit that reverses an earlier commit.

```bash
git revert COMMIT_ID
```

Example:

```bash
git revert a1b2c3d
```

### Reset vs Revert

| Reset                 | Revert                     |
| --------------------- | -------------------------- |
| Moves branch history  | Creates a new commit       |
| Can rewrite history   | Preserves existing history |
| Useful for local work | Safer for shared branches  |

---

# 17. 📜 Git Log

Show commit history:

```bash
git log
```

Short format:

```bash
git log --oneline
```

Show all branches:

```bash
git log --oneline --all
```

Graph:

```bash
git log --oneline --graph --all
```

Latest commit:

```bash
git log -1
```

---

# 18. 🏷️ Git Tag

Tags are used to mark important points in Git history, commonly releases.

Create tag:

```bash
git tag v1.0
```

Create annotated tag:

```bash
git tag -a v1.0 -m "Version 1.0"
```

List tags:

```bash
git tag
```

Show tag:

```bash
git show v1.0
```

Push one tag:

```bash
git push origin v1.0
```

Push all tags:

```bash
git push origin --tags
```

Delete local tag:

```bash
git tag -d v1.0
```

Delete remote tag:

```bash
git push origin --delete v1.0
```

---

# 19. 📦 Git Stash

`git stash` temporarily stores uncommitted changes.

## Stash Changes

```bash
git stash
```

Add message:

```bash
git stash push -m "My changes"
```

List stashes:

```bash
git stash list
```

Apply latest stash:

```bash
git stash apply
```

Apply specific stash:

```bash
git stash apply stash@{0}
```

Apply and remove:

```bash
git stash pop
```

Delete one stash:

```bash
git stash drop stash@{0}
```

Delete all stashes:

```bash
git stash clear
```

Show stash:

```bash
git stash show
```

Show complete changes:

```bash
git stash show -p
```

---

# 20. 🌿 Git Branch

A branch allows you to work on a separate line of development.

## List Branches

```bash
git branch
```

All local and remote branches:

```bash
git branch -a
```

## Create Branch

```bash
git branch feature
```

## Switch Branch

```bash
git switch feature
```

Older command:

```bash
git checkout feature
```

## Create and Switch

```bash
git switch -c feature
```

Older command:

```bash
git checkout -b feature
```

## Rename Current Branch

```bash
git branch -M main
```

Rename another branch:

```bash
git branch -m old-name new-name
```

## Delete Local Branch

```bash
git branch -d feature
```

Force delete:

```bash
git branch -D feature
```

## Delete Remote Branch

```bash
git push origin --delete feature
```

## Push New Branch

```bash
git push -u origin feature
```

After tracking is established:

```bash
git push
```

## Show Current Branch

```bash
git branch --show-current
```

---

# 21. 🔀 Git Merge

Merge another branch into the current branch.

Switch to the target branch:

```bash
git switch main
```

Merge feature branch:

```bash
git merge feature
```

### Merge Flow

```text
             main
              │
              │
              ├───────────────┐
              │               │
              │           feature
              │               │
              │               │
              │<──────────────┘
              │
             Merge
```

If conflicts occur:

```bash
git status
```

Fix the conflicted files, then:

```bash
git add .
git commit
```

---

# 22. 🌐 Remote Repository Commands

Add remote:

```bash
git remote add origin URL
```

Show remote:

```bash
git remote -v
```

Change remote URL:

```bash
git remote set-url origin URL
```

Remove remote:

```bash
git remote remove origin
```

Show remote details:

```bash
git remote show origin
```

---

# 23. 🔎 Useful Git Commands

### Git Version

```bash
git --version
```

### Repository Status

```bash
git status
```

### Show Changes

```bash
git diff
```

### Show Staged Changes

```bash
git diff --staged
```

### Add File

```bash
git add filename
```

### Add All Files

```bash
git add .
```

### Commit

```bash
git commit -m "message"
```

### Commit History

```bash
git log
```

### Short History

```bash
git log --oneline
```

### Current Branch

```bash
git branch --show-current
```

### Fetch Remote Changes

```bash
git fetch
```

### Pull Remote Changes

```bash
git pull
```

### Push Changes

```bash
git push
```

---

# 24. 🚀 Complete Git Workflow

```text
             Create / Modify File
                     │
                     ▼
                git status
                     │
                     ▼
                  git add
                     │
                     ▼
               Staging Area
                     │
                     │ git commit
                     ▼
              Local Repository
                     │
                     │ git push
                     ▼
                   GitHub
                     │
                     │ git pull
                     ▼
             Updated Local Code
```

### Commands

```bash
git status

git add .

git status

git commit -m "Added new feature"

git push
```

---

# 25. 🧑‍💻 Complete Project Example

Create project:

```bash
mkdir quickloan
cd quickloan
```

Initialize Git:

```bash
git init
```

Create files:

```bash
touch index.html
touch README.md
```

Check status:

```bash
git status
```

Add files:

```bash
git add .
```

Check staging:

```bash
git status
```

Commit:

```bash
git commit -m "Initial commit"
```

Rename branch:

```bash
git branch -M main
```

Add GitHub remote:

```bash
git remote add origin https://github.com/USERNAME/quickloan.git
```

Push:

```bash
git push -u origin main
```

---

# 26. 📚 Git Command Cheat Sheet

| Command         | Purpose                        |
| --------------- | ------------------------------ |
| `git --version` | Check Git version              |
| `git config`    | Configure Git                  |
| `git init`      | Initialize repository          |
| `git status`    | Check repository status        |
| `git add`       | Add files to staging           |
| `git commit`    | Save changes                   |
| `git push`      | Upload changes                 |
| `git pull`      | Download and integrate changes |
| `git fetch`     | Download remote information    |
| `git clone`     | Copy remote repository         |
| `git log`       | Show commit history            |
| `git diff`      | Show changes                   |
| `git restore`   | Restore files                  |
| `git reset`     | Reset changes/commits          |
| `git revert`    | Reverse a commit               |
| `git stash`     | Temporarily save changes       |
| `git tag`       | Create version tags            |
| `git branch`    | Manage branches                |
| `git switch`    | Switch branches                |
| `git merge`     | Merge branches                 |
| `git remote`    | Manage remote repositories     |
| `git rm`        | Remove tracked files           |

---

# 🎯 Git Learning Flow

```text
Git Installation
       ↓
Git Configuration
       ↓
git init
       ↓
git status
       ↓
git add
       ↓
Staging Area
       ↓
git commit
       ↓
Local Repository
       ↓
git remote
       ↓
git push
       ↓
GitHub
       ↓
git pull / fetch
       ↓
Branches
       ↓
Merge
       ↓
Stash
       ↓
Reset / Revert
       ↓
Tags
       ↓
.gitignore
       ↓
GitHub Fork + Pull Request
```

---

# ⭐ Most Important Commands for Interviews

```bash
git init
git status
git add .
git commit -m "message"
git push
git pull
git clone
git fetch
git log
git diff
git branch
git switch
git merge
git stash
git reset
git revert
git tag
git remote
git restore
git rm
```

---

# 👨‍💻 Author

**Prince Vaghasiya**

---

## ⭐ Support

If this README helped you learn Git and GitHub, give this repository a ⭐ and keep learning **Git, GitHub, Linux, AWS and DevOps**!
