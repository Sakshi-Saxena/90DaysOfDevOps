# Git Commands Cheat Sheet

---

## 🔹 Setup & Config

| Command                                     | What it does                     |
| ------------------------------------------- | -------------------------------- |
| `git config --global user.name "Your Name"` | Sets global username             |
| `git config --global user.email "email"`    | Sets global email                |
| `git config --list`                         | Shows current Git configuration  |
| `git init`                                  | Initializes a new Git repository |

---

## 🔹 Basic Workflow

| Command               | What it does                             |
| --------------------- | ---------------------------------------- |
| `git status`          | Shows current state of working directory |
| `git add <file>`      | Stages a specific file                   |
| `git add .`           | Stages all changes                       |
| `git commit -m "msg"` | Saves staged changes as a commit         |
| `git log`             | Shows commit history                     |
| `git log --oneline`   | Compact commit history                   |
| `git diff`            | Shows unstaged changes                   |
| `git diff --staged`   | Shows staged changes                     |

---

## 🔹 Branching

| Command                  | What it does                 |
| ------------------------ | ---------------------------- |
| `git branch`             | Lists branches               |
| `git branch <name>`      | Creates a new branch         |
| `git branch -d <name>`   | Deletes a branch safely      |
| `git checkout <branch>`  | Switches branch (old method) |
| `git checkout -b <name>` | Creates + switches branch    |
| `git switch <branch>`    | Switches branch (modern)     |
| `git switch -c <name>`   | Creates + switches branch    |

---

## 🔹 Remote Operations

| Command                       | What it does                      |
| ----------------------------- | --------------------------------- |
| `git clone <url>`             | Copies repo to local machine      |
| `git remote -v`               | Lists remote repositories         |
| `git remote add origin <url>` | Adds remote repo                  |
| `git push origin <branch>`    | Pushes changes to remote          |
| `git pull origin <branch>`    | Fetch + merge changes             |
| `git fetch origin`            | Downloads changes without merging |

### Fork Workflow

| Command                         | What it does                  |
| ------------------------------- | ----------------------------- |
| `git clone <fork-url>`          | Clones your fork              |
| `git remote add upstream <url>` | Adds original repo            |
| `git fetch upstream`            | Fetches original repo changes |
| `git merge upstream/main`       | Syncs fork with original      |

---

## 🔹 Merging & Rebasing

| Command                       | What it does                               |
| ----------------------------- | ------------------------------------------ |
| `git merge <branch>`          | Merges branch into current                 |
| `git merge --squash <branch>` | Combines commits into one                  |
| `git rebase <branch>`         | Reapplies commits on top of another branch |
| `git rebase -i HEAD~n`        | Interactive rebase (edit/squash commits)   |

---

## 🔹 Stash & Cherry Pick

| Command                  | What it does              |
| ------------------------ | ------------------------- |
| `git stash`              | Temporarily saves changes |
| `git stash list`         | Lists stashes             |
| `git stash apply`        | Applies stash (keeps it)  |
| `git stash pop`          | Applies and removes stash |
| `git stash drop`         | Deletes stash             |
| `git cherry-pick <hash>` | Applies specific commit   |

---

## 🔹 Reset & Revert

| Command                    | What it does                     |
| -------------------------- | -------------------------------- |
| `git reset --soft HEAD~1`  | Undo commit, keep staged changes |
| `git reset --mixed HEAD~1` | Undo commit, unstage changes     |
| `git reset --hard HEAD~1`  | Deletes commits and changes      |
| `git revert <hash>`        | Creates commit to undo changes   |

---

## 🔹 Reflog

| Command                     | What it does                  |
| --------------------------- | ----------------------------- |
| `git reflog`                | Shows history of HEAD changes |
| `git reset --hard HEAD@{n}` | Restores previous state       |

---

## 🔹 Amend

| Command                       | What it does                |
| ----------------------------- | --------------------------- |
| `git commit --amend`          | Modifies last commit        |
| `git commit --amend -m "msg"` | Updates last commit message |

---

## 🔑 Quick Notes

* `reset` → rewrites history
* `revert` → safe undo
* `stash` → temporary storage
* `rebase` → clean linear history
* `merge` → preserves history

