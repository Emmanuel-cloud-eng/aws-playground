# Day 2 — Git Workflow Notes

**Date:** 2026-08-15
**Practice time:** approximately 2 hours

---

## The Mental Model That Helped Me

The four stages of Git are:
first writing or creating the codes on you local computer
second git status = used to check our current situation in the project. 
git add = is the staging area, thing of it as packing all your code in a box before before sending it to github.
git commit is when you are sure of things and have commited to send these codes to github. you add a commit message here a brief description of what you changed, added or deleted.
git push is when you push your code to github cloud.

---

## Commands I Practiced Today

### git status
**What it does:** Show me exactly what is happening in my project right now
**When I use it:** A lot actually after staging, after committing, after pushing.
**Example output when everything is clean:** 


### git diff
**What it does:** shows you what has currently changed in your project 
**Key variants:**
- `git diff` — to see changes in your working that have not been staged yet
- `git diff --staged` — to see chnages you have put into your staging area but not committed
- `git diff --stat` — shows a summary of your changes 
- `git diff HEAD~1` — to see what has change between your HEAD  your current commit and the commit right before it

### git add
**What it does:** stages your changes to prepare them for commit
**Key variants:**
- `git add filename` — when you want to stage a specific file
- `git add foldername/` — when you want to stage an entire folder
- `git add .` —(when you want to stage every single thing in your working directory

### git commit 
**What it does:** saves your changes as new commits for pushimg into git hub
**The -m flag:** That is the commit message 
**My rules for commit messages:**
1. Must start with a present tense verb (Add, change, remove, modify)
2. Must be descriptive and not vague for the sake of my future self
3. Must not be more than 50 characters

### git push
**What it does:** Used to publish your code to github cloud
**The full command and what each part means:**
`git push origin main`
- `git push` — command to upload to github cloud
- `origin` — The default man for the remote repository I am pushing to on github
- `main` — The branch I am pushing to

### git log
**What it does:** (your description)
**Key variants:**
- git log --oneline — Shows each commit in a short, one-line format.
- git log --oneline --graph — Shows the commit history in a compact graph, making branches and merges easier to understand.
- git log --oneline --stat — Shows each commit in one line plus a summary of which files changed and how many lines were added/removed.
- git show <hash> — Shows details of a specific commit, including its commit message and the actual changes (diff).

### git pull
**What it does:** To download from github cloud to my local machin
**When to use it:** : When you want to get the latest changes from github before continuing your work

---

## Undo Operations

### git restore filename
**What it does:** it restore your local file to what it was on your previous commit
**When to use:** You mistakenly delete your locate file and wants it back
**⚠️ Warning:** You lose your current file 

### git restore --staged filename
**What it does:** Removes filename from the staging area, but keeps your changes in the working directory.

**Difference from git restore:** git restore --staged filename → unstages the changes. Your work is not deleted.

git restore filename → discards the unstaged changes in the file and restores it to the version from the last commit. your work is deleted



---

## My Daily Workflow Checklist

Before starting work:
- [ ] git pull
- [ ] git status

While working:
- [ ] Make your code changes
- [ ]  git diff — review your unstaged changes
- [ ]  git add filename — stage the changes you want to commit

Before ending session:
- [ ] git diff --staged — review what you're about to commit
- [ ] git commit -m "your message" — save your staged changes


---

## Things That Confused Me Today

git log was a bit confusing to me as I kept confusing it with git diff

---

## Things I Want to Learn Next

I guess practice more 