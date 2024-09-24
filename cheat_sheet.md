# **Git Command Cheat Sheet**

## **1. Git Configuration**

### **Set up user details:**
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```
- **Flags**:
  - `--global`: Applies settings globally for all repositories on your machine.
  - `--list`: View current configuration.

---

## **2. Initialize a Repository**

### **Create a new local Git repository:**
```bash
git init
```
- This creates an empty `.git` directory to track your project.

---

## **3. Checking Repository Status**

### **Check the current state of the working directory and staging area:**
```bash
git status
```
- Shows which files have changes and what actions are needed (e.g., staging or committing changes).

---

## **4. Adding Files to Staging Area**

### **Stage a file for commit:**
```bash
git add <file>
```
- **Flags**:
  - `-p` or `--patch`: Interactively choose hunks of the file to add to the staging area. This allows you to stage some changes from a single file while leaving others out.
  - `-A`: Stage all changes in the working directory. Note: This adds all changes within the git repository regardless of the current directory.
- Example: `git add demo.txt`

### **Stage all modified files:**
similar to`git add -A` but only stages changes in current directory
```bash
git add .
```
- Stages all changes in the current directory.

---

## **5. Committing Changes**

### **Commit changes with a message:**
```bash
git commit -m "Your commit message"
```
- Example: `git commit -m "Add new feature"`
  
### **Amend the last commit (edit message or include staged changes):**
```bash
git commit --amend
```

---

## **6. Viewing Commit History**

### **Show commit history:**
```bash
git log
```
- **Flags**:
  - `--oneline`: Show each commit in a single line.
  - `--graph`: Show a visual representation of the branch structure.
  - `--abbrev-commit`: Show each commit with a shortened hash
  - Example: `git log --oneline --graph`

---

## **7. Branching and Merging**

### **Create a new branch:**
```bash
git branch <branch_name>
```
- Example: `git branch new-feature`

### **Switch to a branch:**
```bash
git checkout <branch_name>
```
- Example: `git checkout main`

### **Create a new branch and switch to it:**
```bash
git checkout -b <branch_name>
```
- Example: `git checkout -b new-feature`

### **Merge a branch into the current branch:**
```bash
git merge <branch_name>
```
- Example: `git merge new-feature`

---

## **8. Remote Repositories**

### **Add a remote repository:**
```bash
git remote add origin <remote_url>
```
- Example: `git remote add origin git@github.com:yourusername/repo.git`

### **View remotes:**
```bash
git remote -v
```

---

## **9. Pushing and Pulling Changes**

### **Push commits to a remote repository:**
```bash
git push origin <branch_name>
```
- Example: `git push origin main`

### **Push commits and set upstream for future pushes:**
```bash
git push -u origin <branch_name>
```

### **Pull changes from a remote repository:**
```bash
git pull
```
- Fetch and merge changes from the remote repository into your local branch.

---

## **10. Cloning a Repository**

### **Clone a remote repository to your local machine:**
```bash
git clone <repository_url>
```
- Example: `git clone git@github.com:yourusername/repo.git`

---

## **11. Viewing Differences**

### **View changes that have not been staged:**
```bash
git diff
```

### **View changes between staged files and the last commit:**
```bash
git diff --staged
```

---

## **12. Working with Tags**

### **Create a new tag:**
```bash
git tag <tag_name>
```
- Example: `git tag v1.0.0`

### **Push tags to a remote repository:**
```bash
git push origin --tags
```

---

## **13. Deleting Branches**

### **Delete a local branch:**
```bash
git branch -d <branch_name>
```
- Example: `git branch -d new-feature`

---

## **14. Resetting Changes**

### **Unstage a file (but keep changes in the working directory):**
```bash
git reset <file>
```

### **Discard changes in the working directory (irreversible):**
```bash
git checkout -- <file>
```
- Example: `git checkout -- demo.txt`

---

## **15. Viewing Remote Branches**

### **List all branches, local and remote:**
```bash
git branch -a
```

---

## **16. Rebasing**

### **Rebase your current branch onto another:**
```bash
git rebase <branch_name>
```
- Example: `git rebase main`

---

## **17. Stashing Changes**

### **Save changes temporarily and clean the working directory:**
```bash
git stash
```

### **Apply stashed changes:**
```bash
git stash apply
```

---

## **Common Git Flags Summary**

- `-m "message"`: Add a commit message.
- `--global`: Apply globally to all repositories.
- `-u`: Set upstream branch (for push).
- `-d`: Delete branch.
- `-b`: Create and switch to a new branch.
- `--oneline`: Show a condensed log.
