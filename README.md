# Udemy.GitBasics — Git Fundamentals Practice Repo

This repository contains **small, focused exercises** I completed while finishing the Udemy course:
**“Git & GitHub – The Practical Guide”**.

It is intentionally simple (mostly `.txt` files) because the goal is to learn **Git mechanics**:
commits, branches, HEAD, detached HEAD, resets, merges, and `.gitignore`.

---

## What I practiced here

- Creating commits and understanding snapshots
- Inspecting history (`git log`)
- Branch creation / switching and why branches matter
- Understanding `HEAD` and working in a **detached HEAD** state
- Merging experiments back into `main`
- Undoing mistakes with `git reset` (and learning what changes in HEAD / index / working tree)
- Using `.gitignore` to ignore generated/unwanted files

---

## Repository structure

| Path | Purpose |
|------|---------|
| `initial-commit.txt` | First commit / initial state practice |
| `working-with-branches.txt` | Notes after practicing branches |
| `detached-head.txt` | Detached HEAD exploration |
| `dummy.txt` | Used to practice reset / undo scenarios |
| `.gitignore` + `test.log` | Ignore rules experiment |

---

## Key Git commands used (core set)

> Exact flags/options can vary, but these are the commands I used to perform the actions reflected in the reflog.

```bash
# init + first commit
git init
git status
git add .
git commit -m "initial commit"

# history
git log --oneline --graph --decorate

# branching
git branch
git switch -c second-branch
git switch main

# detached HEAD exploration
git checkout <commit>
# (detached HEAD state)
git switch main

# merging
git merge <branch-name>

# undo / reset
git reset HEAD~1
git reset <commit-sha>

# ignore rules
echo "*.log" >> .gitignore
git add .gitignore
git commit -m "add gitignore"
