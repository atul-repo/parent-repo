# 🧭 Parent Repository – Monorepo with Git Submodules

Welcome to the **parent-repo**. This is the central repository that organizes and manages all team-level codebases using **Git submodules**, including shared libraries and microservices.

---

## 📁 Repository Structure

```text
parent-repo/
├── common-lib/        # Shared library used across teams
├── team-A-app/        # Application owned by Team A
│   └── subteam-A/     # Nested submodule for Subteam A
├── team-B-app/        # Application owned by Team B
│   └── subteam-B/     # Nested submodule for Subteam B

## To clone this repository along with all submodules and nested submodules:

git clone git@github.com:atul-repo/parent-repo.git
cd parent-repo
git submodule update --init --recursive
##########################################################################
# If submodules are in detached HEAD, switch to branch (e.g., main)
git submodule foreach --recursive 'git checkout main && git pull'

# After pulling parent repo, sync submodules:
git pull && git submodule update --init --recursive

## Recursive Submodules: If you have nested submodules (submodules within submodules), you might want to use the --recursive flag:
git submodule foreach --recursive git checkout main

##Recursive Status with Branch Information
git status && git submodule foreach --recursive 'echo "\nSUBMODULE: $path"; git status; git branch --show-current'
# For branch awareness → git status && git submodule foreach --recursive git branch --show-current
# For detailed changes → git status && git submodule foreach --recursive git status

##quick and effective way to remove a Git submodule ##
git submodule deinit -f <path> && git rm -f <path> && rm -rf .git/modules/<path>

📌 Example:
If your submodule is subteam-A, you’d run:
git submodule deinit -f subteam-A && git rm -f subteam-A && rm -rf .git/modules/subteam-A
Then commit and push:
git commit -m "Removed submodule subteam-A"
git push origin main


