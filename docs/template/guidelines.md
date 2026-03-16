# Student Guide — How to Submit Course Notes on GitHub

> **Course:** SDA202 / CSF303 | **Organisation:** swe-cst
> Read this guide completely before doing anything. Every step matters.

---

## Table of Contents

1. [One-Time Setup](#1-one-time-setup)
2. [Fork the Repo](#2-fork-the-repo)
3. [Clone Your Fork](#3-clone-your-fork)
4. [Claim Your Topic](#4-claim-your-topic)
5. [Create a Branch](#5-create-a-branch)
6. [Write Your Notes](#6-write-your-notes)
7. [Preview Your Notes](#7-preview-your-notes)
8. [Submit Your Notes](#8-submit-your-notes)
9. [After Your PR is Reviewed](#9-after-your-pr-is-reviewed)
10. [Notes File Template](#10-notes-file-template)
11. [Quick Reference Cheat Sheet](#11-quick-reference-cheat-sheet)
12. [Common Errors and Fixes](#12-common-errors-and-fixes)

---

## 1. One-Time Setup

Update your github username and email address linked to github account in this sheet : [Github User Information](https://docs.google.com/spreadsheets/d/17YRIAQiOMS6JhViD6Bp3cl-sabhHaBpF/edit?gid=914276829#gid=914276829)

### 1.1 Accept the Organisation Invitation

After module tutors adds you:

1. Check your email for an invitation from GitHub
2. Click **"Accept invitation"** in the email
3. You now have access to the course repository

⚠️ Invitations **expire after 7 days**. Accept it immediately.

---

### 1.2 Install Git (Ignore if already installed)

Git is the tool that tracks and saves your changes.

**Windows:**

1. Go to [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. Download and run the installer
3. Keep **all default settings** and click Next through everything
4. After install, search for **Git Bash** in the Start Menu and open it

**Mac:**

1. Open **Terminal** (search for it in Spotlight)
2. Type `git --version` and press Enter
3. If Git is not installed, macOS will prompt you to install it automatically — click Install

**Linux:**

```bash
sudo apt install git
```

**Verify Git is installed:**

```bash
git --version
# You should see something like: git version 2.43.0
```

---

### 1.3 Set Up Your Identity in Git

Git needs to know who you are. Open Git Bash (Windows) or Terminal (Mac/Linux) and run:

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your-student-email@university.ac.ke"
```

**Example:**

```bash
git config --global user.name "Dorji Tshomo"
git config --global user.email "dorji.tshomo@university.ac.ke"
```

> ✅ This is done **once only**. Git uses this on every commit you make.

---

### 1.4 Install Python ( if not already installed)

Python is needed to preview your notes before submitting.

### 1.5 Install MkDocs

MkDocs turns your markdown notes into a website for previewing.

```bash
pip install mkdocs-material
```

**Verify MkDocs is installed:**

```bash
mkdocs --version
# You should see something like: mkdocs, version 1.5.3
```

---

## 2. Fork the Repo

> Forking creates **your own personal copy** of the course repo. You work on your copy, then send your work back to the lecturer.

1. Go to your course repository:
   - **SDA202 students:** [Repo Link](https://github.com/swe-cst/sda202)

2. Click the **Fork** button at the top-right of the page

3. On the next screen, click **"Create fork"**

4. GitHub creates your copy at:  
   `https://github.com/YOUR-USERNAME/sda202`

---

## 3. Clone Your Fork

> Cloning downloads your fork to your computer so you can work on it.

Open Git Bash or Terminal and run:

```bash
# Replace YOUR-USERNAME and the repo name with yours
git clone https://github.com/YOUR-USERNAME/sda202.git
```

Move into the downloaded folder:

```bash
cd sda202
```

Now connect your local copy to the **original lecturer's repo** so you can receive updates:

```bash
git remote add upstream https://github.com/SWE-software-engineering/sda202.git
```

Verify it worked:

```bash
git remote -v
```

You should see:

```
origin    https://github.com/YOUR-USERNAME/sda202.git (fetch)
origin    https://github.com/YOUR-USERNAME/sda202.git (push)
upstream  https://github.com/SWE-software-engineering/sda202.git (fetch)
upstream  https://github.com/SWE-software-engineering/sda202.git (push)
```

> - **origin** = your personal fork (you push here)
> - **upstream** = the lecturer's original repo (you pull updates from here)

---

## 4. Claim Your Topic

> ⚠️ **Do NOT start writing until your topic is approved.**  
> Two students cannot submit notes on the same topic.

1.  Go to the course repo Issues page:
    - SDA202: [Repo Issue Page](https://github.com/swe-cst/sda202/issues)

2.  Click **"New issue"**

3.  Select **"Claim a Topic"** template Example: [Claim a topic](claim-topic.md)

4.  Fill in:
    - Your full name
    - Your student ID
    - Your GitHub username
    - The week number and topic title

5.  Click **"Submit new issue"**

6.  Wait for your tutor to comment **"✅ Approved — go ahead"**

---

## 5. Create a Branch

> A branch is your own isolated workspace. It keeps your work separate from everyone else's until it is reviewed and approved.

**Always do this before writing anything:**

```bash
# First, make sure you have the latest version
git pull upstream main

# Create and switch to a new branch
# Name it after your topic — be descriptive
git checkout -b week3-sorting-algorithms
```

**Good branch names:**

```
✅ week3-sorting-algorithms
✅ week4-binary-trees
✅ week5-database-normalisation
```

**Bad branch names:**

```
❌ mynotes
❌ branch1
❌ test
```

Verify you are on your new branch:

```bash
git branch
# The branch with * next to it is your current branch
# * week3-sorting-algorithms
#   main
```

---

## 6. Write Your Notes

### 6.1 Create Your Notes File

Your file **must be named after your GitHub username**. This is how the system knows the file belongs to you.

Navigate to the correct week folder and create your file:

```
docs/
└── unit2/
    └── your-github-username.md   ← YOUR file
```

In VS Code, open the project folder:

```bash
code .
```

Then navigate to `docs/weekX/` and create a new file named `your-github-username.md`.

> ⚠️ **Never edit another student's file.** The system detects this automatically and your PR will be blocked.

---

### 6.2 Notes File Structure

Your file **must** include these required fields at the top or your PR will be automatically rejected:

```markdown
# Week 3 — Sorting Algorithms

**Contributed by:** Dorji Tshomo  
**Student ID:** 113  
**Date:** 29 Feb 2026  
**Course:** SDA202

---
```

See the full [Notes File Template](notes.md)

!!! danger "Remember"

      Before committing and push it make sure to add your note in th emkdocs.yml file

      1. Go the last part of the mkdocs.yml file and under nav
      2. if your UNit is not mentioned mention your specific unit Example - Unit 2
      3. Ensure proper indentation or else it will not work.
      4. Ensure Proper naming of the section topic

         ```
         - Unit 1:
         - Objective: unit1/objective.md
         - 1.1 Introduction: unit1/your-github-username.md

         ```

---

## 7. Preview Your Notes

> Always preview **before** submitting. Broken formatting will fail the automated checks.

In your terminal, make sure you are inside the project folder, then run:

```bash
mkdocs serve
```

Open your browser and go to:

```
http://localhost:8000
```

You will see your notes rendered as a full website exactly as they will appear live.

**Check for:**

- ✅ Headings display correctly
- ✅ Code blocks are formatted and coloured
- ✅ No broken links or images
- ✅ Your name, student ID, and date are visible
- ✅ Tables render correctly
- ✅ Spelling is correct

When you are done previewing, press `Ctrl + C` in the terminal to stop.

---

## 8. Submit Your Notes

### 8.1 Stage Your Changes

Check what files you have changed:

```bash
git status
```

Add only **your notes file** — do not add unrelated files:

```bash
# Add your specific file only
git add docs/unit2/your-github-username.md
```

---

### 8.2 Commit With a Clear Message

```bash
git commit -m "Add Week 3 notes on sorting algorithms - Dorji Tshomo"
```

**Good commit messages:**

```
✅ "Add Week 3 notes on sorting algorithms - Dorji"
✅ "Fix typo in Week 3 notes - Sonam"
✅ "Add diagrams to Week 4 binary trees - Penjor"
```

**Bad commit messages:**

```
❌ "update"
❌ "done"
❌ "final"
❌ "notes"
```

---

### 8.3 Push to Your Fork

```bash
# Push to YOUR fork (origin), on YOUR branch
git push origin week3-sorting-algorithms
```

> ⚠️ Always push to `origin` (your fork), never to `upstream` (the lecturer's repo).

---

### 8.4 Open a Pull Request

1. Go to your fork on GitHub:  
   `https://github.com/YOUR-USERNAME/sda202`

2. You will see a yellow banner:  
   **"Compare & pull request"** → click it

3. Make sure the PR is going to the **right place**:

   ```
   base repository: SWE-software-engineering/sda202   base: main
   head repository: YOUR-USERNAME/sda202              compare: week3-sorting-algorithms
   ```

4. Fill in the PR form — as per the [PR template](PR.md)

5. Click **"Create pull request"**

---

### 8.5 Automated Checks Will Run

## 9. After Your PR is Reviewed

### If Changes Are Requested

Your tutor will leave comments explaining what to fix. You do not need to open a new PR — just fix and push to the same branch:

```bash
# Make your edits in VS Code, then:
git add docs/week3/your-github-username.md
git commit -m "Fix review comments - corrected formatting - John Mwangi"
git push origin week3-sorting-algorithms
```

The PR updates automatically.

---

### If Your PR is Approved and Merged 🎉

Your notes are now live on the course website!

Clean up your local machine:

```bash
# Switch back to main
git checkout main

# Pull the latest version (now includes your merged notes)
git pull upstream main

# Delete your old branch — it is no longer needed
git branch -d week3-sorting-algorithms

# Update your fork's main branch too
git push origin main
```

You are now ready to start your **next contribution** from Step 4.

---

---

## 11. Common Errors and Fixes

---

### ❌ "Permission denied" when pushing

**Cause:** You are trying to push to `upstream` (the lecturer's repo) instead of `origin` (your fork).

**Fix:**

```bash
# Wrong ❌
git push upstream main

# Correct ✅
git push origin your-branch-name
```

---

### ❌ "Your branch is behind main"

**Cause:** You forgot to pull the latest changes before starting.

**Fix:**

```bash
git checkout main
git pull upstream main
git checkout your-branch-name
git merge main
```

---

### ❌ Merge conflict

**Cause:** Someone else changed the same file you changed.

**Fix:**

```bash
git pull upstream main
# Open the conflicting file in VS Code
# Look for lines marked with <<<<<<< and >>>>>>>
# Keep YOUR changes, delete the conflict markers
git add .
git commit -m "Resolve merge conflict"
```

---

### ❌ Automated check failing — "File is not named correctly"

**Cause:** Your file is not named after your GitHub username.

**Fix:** Rename the file to match your GitHub username exactly:

```
docs/week3/john-mwangi.md   ← must match GitHub username exactly
```

---

### ❌ Automated check failing — "File is outside docs/ folder"

**Cause:** You accidentally created your file in the wrong location.

**Fix:** Move your file into the correct folder:

```bash
# Move the file to the right place
mv your-file.md docs/week3/your-github-username.md

git add .
git commit -m "Move file to correct folder"
git push origin your-branch-name
```

---

### ❌ `mkdocs serve` gives an error

**Cause:** Usually a formatting mistake in your markdown file.

**Fix:** Read the error message — it tells you the file name and line number.  
Open that line in VS Code and look for broken code blocks, unclosed brackets, or invalid characters.

---

### ❌ "I accidentally edited another student's file"

**Fix:** Do not push. Undo the change immediately:

```bash
# Discard ALL uncommitted changes
git checkout -- .
```

---

> 📌 **Still stuck?** Open an Issue on the course repo describing your problem, or ask your lecturer or classmate for help.

---

## Group Distribution

!!! info "Note"

      Each of the groups will be responsible for maintaining the code for the note of the respective units as mentioned below. The group may decide and assign individual to maintain notes for the particular topic of that unit. Ensure that everyone makes a contribution to the note.

???+ abstract "Group 1 — Unit 2 (Up to 2.3)"

    - YESHEY ZHENNUE
    - UGYEN KINLEY PHUNTSHOK
    - KARMA NAMGAY DORJI
    - NAMGAY LHAMO

??? abstract "Group 2 — Unit 2 (Up to 2.6)"

    - SONAM CHOKI (361)
    - LHUNDUP DORJI
    - SONAM ZANGMO
    - NORBU DHENDUP

??? abstract "Group 3 — Unit 3"

    - SANGAY CHODEN
    - JIGDEN SHAKYA
    - THINLEY DORJI
    - TSHERING NORBU
    - PHUNTSHO NAMGYEL

??? abstract "Group 4 — Unit 4"

    - SONAM WANGMO
    - KARMA CHOING ZANGMO
    - PEMA LOSEL MAURER
    - JIGME NGAWANG CHOGYAL
    - NIDUP DORJI

??? abstract "Group 5 — Unit 5"

    - Nyendrak Yoezer Zangmo
    - Sherab Nima Rigzin
    - Kinley Tobgay Lhendrup
    - Gayley Choden
    - Tandin Wangchuk

??? abstract "Group 6 — Unit 6"

    - Sonam Choki (360)
    - Yeshey Lhaden
    - Sonam Dorji
    - Sangay Tenzin
    - Wangchuk Gyeltshen Zangpo

_Guide maintained by the Norbu, SWE Programme_
