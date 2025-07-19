# 🧠 Git Command Cheatsheet

## 🔍 View Repository Size

```bash
curl -s https://api.github.com/repos/ameerzada2000/y1001 | jq '.size' | numfmt --to=iec --from-unit=1024
```

---

## 🚫 Remove Specific Files from Staging

```bash
git restore --staged <file>
```

## 🔄 Remove All Files from Staging

```bash
git reset
```

---

## ⏪ Undo Local Commits

- Retain your work:

```bash
git reset --soft HEAD~1
```

- Remove work as well:

```bash
git reset --hard HEAD~1
```

- Alternative:

```bash
git reset --soft origin/<branch-name>
```

---

## 📝 Edit Last Commit

```bash
git commit --amend
```

---

## 🌿 Delete Branch (Local and Remote)

```bash
git branch -D branch_name
git push origin :branch_name
```

---

## 🔄 Pull Feature Branch to Merge into Main

```bash
git pull origin develop
```

---

## 🩹 Patches

- Create a patch with all changes:

```bash
git diff > /home/abhishek/patch_file_name.patch
```

- Apply patch:

```bash
git apply patch_file_name.patch
```

- Patch for staged files:

```bash
git diff --cached > /home/abhishek/productcategoryes.patch
```

- Patch for a specific file:

```bash
git diff path/to/file.java > /home/abhishek/patch_file_name.patch
```

- Patch from commit:

```bash
git log --patch -1 <commit-id> > /home/abhishek/patch_file_name.patch
```

---

## 🧳 Git Stash

```bash
git stash                     # Create stash
git stash pop                 # Apply and remove latest stash
git stash list                # List all stashes
git stash drop                # Drop all stashes
git stash push -m "msg"       # Stash with a message
git stash pop stash@{n}       # Pop specific stash
git stash apply stash@{n}     # Apply specific stash
git stash show -p stash@{n} > name.patch  # Patch from stash
```

---

## ⚙️ Git User Config

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global user.password "yourpassword"
```

---

## 🧹 Clean Untracked Files

```bash
git clean -fx      # Force clean untracked files
git clean -n       # Dry run
git clean -f       # Untracked files
git clean -f -d    # Also directories
git clean -f -x    # Include .gitignore'd files
git clean -i       # Interactive
```

---

## 🧯 Revert Pushed Commit & Retain Work

```bash
git log                       # Copy second-last commit ID
git reset <commit-id>        # Reset to that commit
git push origin branch-name -f  # Force push
```

---

## 🍒 Cherry Pick a Commit

```bash
git cherry-pick <commitHash>
```

---

## 🔐 Git Credential Storage

```bash
git config --local credential.helper store     # Store credentials
git config --local credential.helper ''        # Remove stored credentials
```

---

## 🌍 Set Remote URL with Username

```bash
git remote set-url origin https://username@<repo-url>
```

---

## 📋 Commit with Changelog Trailer

```bash
git commit --trailer Changelog:Changed -m "message"
git commit --trailer Changelog:Added -m "message"
```

---

## 🧨 Delete All Local Branches Except `develop`

```bash
git branch | grep -v 'develop' | xargs git branch -D
```

---

## 🔧 Create Patch with No Prefix

```bash
git diff --no-prefix path/to/file.ftl > /home/common/Test.patch
```