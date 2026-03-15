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

# history
git log --oneline --graph --decorate
git reflog


69dd2da (HEAD -> main, origin/main) HEAD@{0}: commit: after more than reset
580bd64 HEAD@{1}: reset: moving to head~1
ca087aa HEAD@{2}: reset: moving to head~1
e74f3d0 HEAD@{3}: reset: moving to Head~1
42c579a HEAD@{4}: commit: add gitignore
e74f3d0 HEAD@{5}: merge detached-head-2: Merge made by the 'ort' strategy.
ca087aa HEAD@{6}: checkout: moving from detached-head-2 to main
7f8fac8 HEAD@{7}: checkout: moving from main to detached-head-2
ca087aa HEAD@{8}: checkout: moving from 7f8fac8c00c59937b4a2af08f7a04ca21bedfa08 to main
7f8fac8 HEAD@{9}: commit: text added in detached
580bd64 HEAD@{10}: checkout: moving from main to 580bd64e58cbcdbb6cf19c52d071d7c4e810ab8c
ca087aa HEAD@{11}: merge detachec-head: Merge made by the 'ort' strategy.
580bd64 HEAD@{12}: checkout: moving from detachec-head to main
e0c1492 HEAD@{13}: checkout: moving from main to detachec-head
580bd64 HEAD@{14}: checkout: moving from e0c1492a01037901bfad648dfbb5b313ea5b6123 to main
e0c1492 HEAD@{15}: commit: changes made in detached
497e70f HEAD@{16}: checkout: moving from main to 497e70f204c90c00b2ef348469de9d8ce0008f79
580bd64 HEAD@{17}: commit: add dummy txt file
497e70f HEAD@{18}: reset: moving to HEAD~1
e546734 HEAD@{19}: commit: unrequired file added again
497e70f HEAD@{20}: reset: moving to HEAD~1
e719662 HEAD@{21}: commit: unrequierd file added again
497e70f HEAD@{22}: reset: moving to HEAD~1
73f11dc HEAD@{23}: commit: unrequierd file added again
497e70f HEAD@{24}: reset: moving to HEAD~1
cc71a4c HEAD@{25}: commit: unrequired file added
497e70f HEAD@{26}: reset: moving to HEAD
497e70f HEAD@{27}: commit: delete file form working directory
0325356 HEAD@{28}: checkout: moving from forth-branch to main
0325356 HEAD@{29}: checkout: moving from main to forth-branch
0325356 HEAD@{30}: merge third-branch: Fast-forward
35aff56 HEAD@{31}: checkout: moving from third-branch to main
0325356 HEAD@{32}: commit: add branches text file
35aff56 HEAD@{33}: checkout: moving from second-branch to third-branch
35aff56 HEAD@{34}: checkout: moving from main to second-branch
35aff56 HEAD@{35}: checkout: moving from second-branch to main
35aff56 HEAD@{36}: checkout: moving from main to second-branch
35aff56 HEAD@{37}: checkout: moving from 35aff56281d73ead0e9218ce8c1f275f994579e2 to main
35aff56 HEAD@{38}: checkout: moving from main to 35aff56281d73ead0e9218ce8c1f275f994579e2
35aff56 HEAD@{39}: checkout: moving from 49ddb399b133633b7a285898da0a0a8154958ed0 to main
49ddb39 HEAD@{40}: checkout: moving from main to 49ddb399b133633b7a285898da0a0a8154958ed0
35aff56 HEAD@{41}: commit: added second .txt file
49ddb39 HEAD@{42}: commit (initial): add first .txt file
