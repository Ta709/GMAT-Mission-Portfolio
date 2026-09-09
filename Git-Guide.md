# Git Guide — GMAT Mission Portfolio

This is a quick reference for updating the GMAT Mission Portfolio on GitHub.

The basic workflow is:

```text
Edit files
   ↓
Test in GMAT
   ↓
Check changes
   ↓
git add
   ↓
git commit
   ↓
git push
   ↓
GitHub
```

---

# 1. Open Git Bash

Open **Git Bash**.

Navigate to the portfolio:

```bash
cd ~/CODE/GMAT-Portfolio
```

Check that you're in the right place:

```bash
pwd
```

You should see something similar to:

```text
/c/Users/comp/CODE/GMAT-Portfolio
```

---

# 2. Check Git Status

Before doing anything, run:

```bash
git status
```

This tells you what has changed since your last commit.

For example:

```text
On branch main

Changes not staged for commit:
    modified: Project 01 — Circular Earth Orbit/learning-log.md
```

This means you changed a file, but Git hasn't prepared it for the next commit yet.

---

# 3. Add Your Changes

To add everything you've changed:

```bash
git add .
```

The `.` means:

> Add all changes inside the current repository.

Then check:

```bash
git status
```

You should see something like:

```text
Changes to be committed:
    modified: Project 01 — Circular Earth Orbit/learning-log.md
```

---

# 4. Commit Your Changes

A commit is a **saved checkpoint in your local Git history**.

Create one with:

```bash
git commit -m "Describe what I changed"
```

Examples:

```bash
git commit -m "Update Project 01 learning log"
```

```bash
git commit -m "Add circular orbit propagation"
```

```bash
git commit -m "Fix Earth force model"
```

Try to make commit messages describe the actual change.

---

# 5. Push to GitHub

Once the commit succeeds:

```bash
git push
```

Because this repository was originally configured with:

```bash
git push -u origin main
```

Git now remembers that `main` should be pushed to GitHub.

So for normal future updates, you usually only need:

```bash
git push
```

---

# 6. The Normal Everyday Workflow

Most of the time, this is all you need:

```bash
cd ~/CODE/GMAT-Portfolio
git status
git add .
git commit -m "Describe my changes"
git push
```

That's it.

---

# 7. When Should I Push?

You DON'T need to push after every tiny edit.

Good times to commit/push:

* A GMAT script successfully runs.
* You finish a small experiment.
* You fix a bug.
* You add a new mission feature.
* You finish a section of a project.
* You update the learning log with an important discovery.
* You reach a meaningful milestone.

For example:

```text
Experiment
    ↓
Get it working
    ↓
Update learning-log.md
    ↓
git add .
    ↓
git commit -m "Add orbital propagation experiment"
    ↓
git push
```

---

# 8. What If I Made a Mistake?

First:

```bash
git status
```

Don't panic.

Git is specifically designed to keep track of changes.

If you haven't committed yet, we can usually fix or undo the changes safely.

**Don't start running random `git reset` or `git clean` commands from the internet.**

If you're unsure, ask for help before using destructive Git commands.

---

# 9. What Does Each Command Mean?

## `git status`

Ask Git:

> "What's going on?"

```bash
git status
```

---

## `git add`

Tell Git:

> "Include these changes in my next checkpoint."

```bash
git add .
```

---

## `git commit`

Tell Git:

> "Save a permanent checkpoint of the staged changes."

```bash
git commit -m "Add orbit propagation"
```

---

## `git push`

Tell Git:

> "Upload my local commits to GitHub."

```bash
git push
```

---

# 10. Local vs GitHub

Remember:

```text
MY COMPUTER

GMAT-Portfolio/
       │
       │
       ├── Git history
       │
       └── latest files
             │
             │ git push
             ▼
          GITHUB
```

A `commit` does **NOT** automatically update GitHub.

A commit only creates a checkpoint on your computer.

`git push` sends those commits to GitHub.

---

# 11. Checking GitHub

After:

```bash
git push
```

open the GitHub repository in your browser and refresh the page.

Your latest files and commits should appear there.

---

# 12. If Git Asks Me to Log In

GitHub may ask you to authenticate.

Follow the authentication process shown by Git/GitHub.

**Never put your GitHub password, personal access token, or authentication code into this file or share it with anyone.**

---

# 13. First-Time Setup Reference

This repository has already been initialized and connected to GitHub.

The setup originally looked like:

```bash
git init
git add .
git commit -m "Start Project 01: Circular Earth Orbit"
git remote add origin https://github.com/ta709/GMAT-Mission-Portfolio.git
git branch -M main
git push -u origin main
```

You normally DO NOT need to repeat these commands.

They were used to create and connect the repository.

---

# 14. Emergency Checklist

If you forget everything:

```bash
cd ~/CODE/GMAT-Portfolio
git status
git add .
git commit -m "Describe what I changed"
git push
```

If something unexpected happens:

**STOP.**

Run:

```bash
git status
```

and read the message before doing anything else.

---

# The Golden Rule

### `add` → `commit` → `push`

```text
git add .
     ↓
prepare changes

git commit -m "..."
     ↓
save checkpoint locally

git push
     ↓
send checkpoint to GitHub
```

That's the Git workflow for this portfolio.
