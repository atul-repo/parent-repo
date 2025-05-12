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
