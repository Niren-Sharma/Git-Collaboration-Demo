# 🚀 Git Collaboration & Merge Conflict Resolution

> **Git Collaboration Workflow**
> A practical demonstration of Git version control, GitHub collaboration, Pull Request workflow, branch management, merge conflict simulation, and conflict resolution.

---

# 📖 Project Overview

This project demonstrates how software developers collaborate efficiently using **Git** and **GitHub** in a real-world development environment.

Instead of making all changes directly on the `main` branch, development is performed on separate feature branches. Once the work is completed, changes are submitted through a **Pull Request (PR)**, reviewed, and merged into the main branch.

To better understand Git's collaborative workflow, this project also intentionally creates a **merge conflict** and resolves it using industry-standard practices.

The entire workflow simulates how multiple developers work on the same project without affecting the production-ready code.

---

# 🎯 Objectives

The primary goals of this project are:

* Understand Git version control.
* Learn GitHub collaboration workflow.
* Create and manage branches.
* Work with commits and commit history.
* Push code to remote repositories.
* Create Pull Requests.
* Simulate merge conflicts.
* Resolve conflicts safely.
* Follow professional Git best practices.

---

# 🛠 Technologies Used

* Git
* GitHub
* Visual Studio Code
* Git Bash / VS Code Terminal
* HTML (Demo File)

---

# 📂 Project Workflow

```
             GitHub Repository
                    │
         Create Repository
                    │
             Clone Repository
                    │
      git checkout -b feature-header
                    │
          Develop New Feature
                    │
          Commit & Push Changes
                    │
          Create Pull Request
                    │
            Merge into main
                    │
──────────────────────────────────
                    │
     Create feature-conflict Branch
                    │
       Modify Same File Locally
                    │
 Modify Same File on Main Branch
                    │
          Open Pull Request
                    │
      ❌ Merge Conflict Appears
                    │
        Pull Latest Main Branch
                    │
      Resolve Conflict in VS Code
                    │
      Commit & Push Resolution
                    │
        Merge Pull Request
                    │
      ✅ Collaboration Completed
```

---

# Step 1 – Repository Initialization

The project began by creating a new GitHub repository initialized with a README file. After creating the repository, it was cloned to the local machine.

### Commands

```bash
git clone <repository-url>
cd git-collaboration-demo
```

### Why was this done?

The remote GitHub repository acts as the central source of truth, while the cloned repository provides a local development environment where code can be written, tested, committed, and synchronized with GitHub.

---

# Step 2 – Feature Branch Development

Instead of writing code directly on the `main` branch, a new feature branch named:

```
feature-header
```

was created.

### Command

```bash
git checkout -b feature-header
```

This command creates a new branch and immediately switches the working directory to it.

A simple `index.html` file was then created containing the project's initial header.

After development, the changes were staged, committed, and pushed.

```bash
git add .
git commit -m "Feat: Add basic header section in index.html"
git push origin feature-header
```

---

# Why Feature Branches?

Working directly on the `main` branch is considered poor practice because unstable code can immediately affect the production version.

Feature branches provide:

* Independent development
* Easier testing
* Better collaboration
* Cleaner Git history
* Safe experimentation

Every new feature should ideally have its own branch.

---

# Step 3 – Pull Request Workflow

Once the feature branch was pushed to GitHub, a Pull Request (PR) was created.

A Pull Request allows developers to:

* Compare changes
* Review code
* Discuss improvements
* Approve modifications
* Merge safely into the main branch

After review, the Pull Request was merged into `main`.

The local repository was then synchronized.

```bash
git checkout main
git pull origin main
```

This ensured that both local and remote repositories contained the same code.

---

# Step 4 – Merge Conflict Simulation

To understand how merge conflicts occur, a conflict was intentionally created.

Two different branches modified the **same line** of the same file.

### Developer A

Edited the `main` branch directly.

### Developer B

Created another branch named

```
feature-conflict
```

and modified the exact same line.

Commands used:

```bash
git checkout -b feature-conflict

git add .

git commit -m "Dev B: Changed header"

git push origin feature-conflict
```

When the Pull Request was opened, GitHub displayed:

```
Can't automatically merge.
```

This happened because Git could not determine which version of the code should be preserved.

---

# What is a Merge Conflict?

A merge conflict occurs whenever Git detects competing changes in the same location of a file.

Git intentionally pauses the merge to prevent accidental loss of code.

Instead of choosing one version automatically, Git asks the developer to decide which code should remain.

This safety mechanism protects collaborative projects from overwriting important work.

---

# Step 5 – Resolving the Conflict

The latest changes from the `main` branch were first pulled into the feature branch.

```bash
git checkout feature-conflict
git pull origin main
```

Git reported a conflict inside `index.html`.

The file contained conflict markers similar to:

```text
<<<<<<< HEAD
Current branch code
=======
Incoming main branch code
>>>>>>> origin/main
```

These markers identify both versions of the conflicting code.

The developer manually removed the markers, selected the correct implementation, and saved the file.

The resolved file was then committed.

```bash
git add index.html

git commit -m "Fix: Resolved merge conflict"

git push origin feature-conflict
```

Once pushed, GitHub automatically recognized that the conflict had been resolved, allowing the Pull Request to be merged successfully.

---

# Git Commands Used

| Command           | Purpose                  |
| ----------------- | ------------------------ |
| `git clone`       | Clone remote repository  |
| `git checkout -b` | Create and switch branch |
| `git add`         | Stage changes            |
| `git commit`      | Save changes locally     |
| `git push`        | Upload commits to GitHub |
| `git pull`        | Download latest changes  |
| `git checkout`    | Switch branches          |

---

# Repository Structure

```
git-collaboration-demo/

│── README.md
│── index.html
```

---

# Key Learnings

Throughout this project, the following concepts were learned:

* Repository management
* Local vs Remote repositories
* Branch creation
* Branch switching
* Commit workflow
* Push and Pull operations
* Pull Requests
* GitHub collaboration
* Merge conflicts
* Conflict resolution
* Team-based development
* Industry Git workflow

---

# Best Practices

✔ Never work directly on the `main` branch.

✔ Create a new branch for every feature.

✔ Pull the latest changes before pushing your work.

✔ Write meaningful commit messages.

✔ Review Pull Requests before merging.

✔ Resolve conflicts carefully instead of deleting code blindly.

✔ Keep repositories well documented.

---

# Real-World Importance

Modern software companies rely heavily on Git and GitHub for collaboration. Multiple developers contribute to the same project simultaneously, making version control essential.

The workflow demonstrated in this project reflects how professional development teams organize their work using feature branches, code reviews, Pull Requests, and conflict resolution before integrating code into the production branch.

Understanding these concepts is a fundamental skill for software engineers and full-stack developers.

---

# Conclusion

This project successfully demonstrated the complete Git collaboration lifecycle—from creating a repository to resolving merge conflicts.

The workflow emphasized safe development practices through feature branches, Pull Requests, and manual conflict resolution, providing practical experience with the collaborative techniques commonly used in professional software development.

By completing this project, I gained hands-on experience with Git branching strategies, repository synchronization, conflict management, and collaborative version control workflows, strengthening my understanding of industry-standard development practices.

---

# 👨‍💻 By: Niren Sharma
