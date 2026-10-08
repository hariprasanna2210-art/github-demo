# GitHub — Start to End Practical Guide

## 1. What is Git?

**Git** is a distributed version control system used to track changes in source code.

Git works locally on your computer.

```text
Developer
   |
   v
Local Project
   |
   | git add
   v
Staging Area
   |
   | git commit
   v
Local Git Repository
   |
   | git push
   v
GitHub Repository
```

---

# 2. What is GitHub?

**GitHub** is a cloud platform that hosts Git repositories.

Git = Version control tool  
GitHub = Online platform for Git repositories

GitHub can be used for:

- Source code hosting
- Team collaboration
- Pull Requests
- Code Reviews
- Issues
- Projects
- Releases
- GitHub Actions / CI/CD
- Documentation
- Open-source projects

---

# 3. Important Git Terminology

| Term | Meaning |
|---|---|
| Git | Version control software |
| GitHub | Cloud platform for Git repositories |
| Repository | Project tracked by Git |
| Commit | Saved snapshot of changes |
| Branch | Separate line of development |
| Main | Primary branch |
| Clone | Download a remote repository |
| Push | Upload local commits to GitHub |
| Pull | Download and integrate remote changes |
| Fetch | Download remote changes without merging |
| Merge | Combine branches |
| Pull Request | Request to merge code |
| Fork | Personal copy of another GitHub repository |
| Tag | Named reference to a commit |
| Release | Published version of a project |
| Remote | Connection to another Git repository |
| Origin | Common name for the GitHub remote |

---

# 4. Install Git

## Windows

Download Git from:

https://git-scm.com/download/win

Install using the default options.

Open:

```text
Git Bash
```

Verify:

```bash
git --version
```

Example:

```text
git version 2.x.x
```

## Ubuntu / Debian

```bash
sudo apt update
sudo apt install git -y
```

Verify:

```bash
git --version
```

---

# 5. Configure Git

Set your username:

```bash
git config --global user.name "Your Name"
```

Set your email:

```bash
git config --global user.email "your-email@example.com"
```

Check configuration:

```bash
git config --global --list
```

Check individual values:

```bash
git config --global user.name
git config --global user.email
```

---

# 6. Create a GitHub Account

Go to:

https://github.com/

Create an account and verify your email address.

After logging in, create a new repository.

Example repository:

```text
github-demo
```

---

# 7. Create Your First Local Project

Create a folder:

```bash
mkdir github-demo
cd github-demo
```

Create a file.

Linux / Git Bash:

```bash
echo "# GitHub Demo" > README.md
```

You can also create the file manually.

Check:

```bash
ls
```

Windows Command Prompt:

```cmd
mkdir github-demo
cd github-demo
```

---

# 8. Initialize Git

Inside the project:

```bash
git init
```

Git creates a hidden directory:

```text
.git
```

Check:

```bash
ls -la
```

You should see:

```text
.git
README.md
```

---

# 9. Check Git Status

```bash
git status
```

You may see:

```text
Untracked files:
  README.md
```

This means Git sees the file but it is not yet being tracked.

---

# 10. Add Files to Staging

Add one file:

```bash
git add README.md
```

Add everything:

```bash
git add .
```

Check:

```bash
git status
```

The file should now appear under:

```text
Changes to be committed
```

---

# 11. Create Your First Commit

```bash
git commit -m "Initial commit"
```

Check:

```bash
git log
```

A shorter version:

```bash
git log --oneline
```

Example:

```text
a1b2c3d Initial commit
```

---

# 12. Connect Local Repository to GitHub

Create an empty repository on GitHub.

Example:

```text
https://github.com/USERNAME/github-demo.git
```

Add it as the remote:

```bash
git remote add origin https://github.com/USERNAME/github-demo.git
```

Check:

```bash
git remote -v
```

Example:

```text
origin  https://github.com/USERNAME/github-demo.git (fetch)
origin  https://github.com/USERNAME/github-demo.git (push)
```

---

# 13. Rename the Branch to Main

```bash
git branch -M main
```

Check:

```bash
git branch
```

Expected:

```text
* main
```

---

# 14. Push Code to GitHub

```bash
git push -u origin main
```

After the first push, you can normally use:

```bash
git push
```

Refresh GitHub and your files should appear.

---

# 15. Complete First-Time Workflow

The basic workflow is:

```bash
mkdir my-project
cd my-project

git init

git add .
git commit -m "Initial commit"

git branch -M main

git remote add origin https://github.com/USERNAME/my-project.git

git push -u origin main
```

---

# 16. Modify a File

Edit:

```text
README.md
```

For example:

```markdown
# My Project

This is my first GitHub project.
```

Check:

```bash
git status
```

Git will show the modified file.

---

# 17. Add and Commit Changes

```bash
git add README.md
git commit -m "Update README"
```

Push:

```bash
git push
```

---

# 18. The Standard Daily Git Workflow

Most developers repeatedly use:

```bash
git status

git add .

git commit -m "Describe the changes"

git push
```

Before starting work, it is usually useful to update your local branch:

```bash
git pull
```

---

# 19. Clone an Existing GitHub Repository

If the project already exists on GitHub:

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

Example:

```bash
git clone https://github.com/example/company-project.git
```

Enter the project:

```bash
cd company-project
```

Check:

```bash
git status
```

---

# 20. Clone a Specific Branch

```bash
git clone -b development https://github.com/USERNAME/REPOSITORY.git
```

---

# 21. Pull Changes

Download and integrate changes from the remote repository:

```bash
git pull
```

Equivalent conceptually to:

```bash
git fetch
git merge
```

---

# 22. Fetch Changes

Fetch remote changes without automatically merging them:

```bash
git fetch
```

View remote branches:

```bash
git branch -r
```

---

# 23. Git Branches

Branches allow developers to work independently.

Example:

```text
main
 |
 +---- development
 |
 +---- feature/login
 |
 +---- feature/payment
```

List branches:

```bash
git branch
```

List local and remote branches:

```bash
git branch -a
```

---

# 24. Create a Branch

```bash
git branch feature-login
```

Switch to it:

```bash
git switch feature-login
```

Modern shortcut:

```bash
git switch -c feature-login
```

Older command:

```bash
git checkout -b feature-login
```

---

# 25. Push a New Branch

```bash
git push -u origin feature-login
```

After that:

```bash
git push
```

---

# 26. Switch Between Branches

```bash
git switch main
```

or:

```bash
git switch feature-login
```

---

# 27. Merge a Branch

First switch to the branch that should receive the changes:

```bash
git switch main
```

Update it:

```bash
git pull
```

Merge:

```bash
git merge feature-login
```

Push:

```bash
git push
```

---

# 28. Delete a Local Branch

After merging:

```bash
git branch -d feature-login
```

Force delete:

```bash
git branch -D feature-login
```

---

# 29. Delete a Remote Branch

```bash
git push origin --delete feature-login
```

---

# 30. GitHub Pull Request

A common team workflow is:

```text
main
  |
  +---- feature/login
            |
            | code
            | commit
            | push
            v
       Pull Request
            |
            v
        Code Review
            |
            v
          Merge
            |
            v
           main
```

Steps:

1. Create a feature branch.
2. Make changes.
3. Commit the changes.
4. Push the branch.
5. Open GitHub.
6. Create a Pull Request.
7. Select the target branch.
8. Add title and description.
9. Request reviewers.
10. Review the code.
11. Fix requested changes if necessary.
12. Merge the Pull Request.

---

# 31. Typical Team Workflow

Start from updated main:

```bash
git switch main
git pull
```

Create a feature branch:

```bash
git switch -c feature/user-login
```

Work on the feature.

Check:

```bash
git status
```

Stage:

```bash
git add .
```

Commit:

```bash
git commit -m "Add user login"
```

Push:

```bash
git push -u origin feature/user-login
```

Then create a Pull Request on GitHub.

---

# 32. Pull Request vs git pull

These are different.

## Pull Request

A GitHub collaboration feature.

It means:

> Please review and merge my branch into another branch.

## git pull

A Git command.

```bash
git pull
```

It downloads and integrates changes from a remote repository.

---

# 33. Git Merge Conflict

A conflict can happen when two branches modify the same part of a file.

Example:

```text
<<<<<<< HEAD
Hello from main
=======
Hello from feature
>>>>>>> feature-login
```

You must manually decide which content should remain.

Then:

```bash
git add .
git commit -m "Resolve merge conflict"
```

Push:

```bash
git push
```

---

# 34. Safer Conflict Workflow

Before starting a feature:

```bash
git switch main
git pull
git switch -c feature-name
```

Before creating a Pull Request, update your branch.

One common approach:

```bash
git fetch origin
git merge origin/main
```

Resolve conflicts if required.

Then:

```bash
git add .
git commit -m "Merge main into feature branch"
git push
```

Your team may instead use rebase. Follow the project's contribution rules.

---

# 35. .gitignore

`.gitignore` tells Git which files should not be committed.

Example:

```gitignore
node_modules/
.env
dist/
build/
.vscode/
.idea/
*.log
.DS_Store
```

For a Node.js project:

```gitignore
node_modules/
.env
dist/
coverage/
*.log
```

---

# 36. Never Commit Secrets

Do NOT commit:

```text
.env
passwords
API keys
private keys
AWS credentials
database passwords
SSH private keys
```

Bad:

```javascript
const password = "MySecretPassword";
```

Better:

```javascript
const password = process.env.DB_PASSWORD;
```

Use `.gitignore`:

```gitignore
.env
```

---

# 37. If a Secret Was Accidentally Committed

Adding it to `.gitignore` is not enough if it was already pushed.

Immediately:

1. Revoke/rotate the secret.
2. Replace the exposed credential.
3. Remove it from the repository/history using an appropriate history-rewriting method.
4. Inform the team if it was a shared repository.

**Important:** Treat an exposed API key/password as compromised.

---

# 38. View Commit History

Full history:

```bash
git log
```

Short history:

```bash
git log --oneline
```

Graph:

```bash
git log --oneline --graph --decorate --all
```

---

# 39. View Changes

Working-tree changes:

```bash
git diff
```

Staged changes:

```bash
git diff --staged
```

---

# 40. Unstage a File

```bash
git restore --staged filename
```

Example:

```bash
git restore --staged app.js
```

---

# 41. Discard Local Changes

For a specific file:

```bash
git restore filename
```

Be careful: this removes uncommitted changes in that file.

---

# 42. Amend the Last Commit

If you forgot to include a file:

```bash
git add forgotten-file.txt
git commit --amend
```

To change only the message:

```bash
git commit --amend -m "Correct commit message"
```

Avoid amending commits that have already been shared unless you understand the consequences.

---

# 43. Git Reset

### Soft reset

Keeps changes staged:

```bash
git reset --soft HEAD~1
```

### Mixed reset

Keeps file changes but unstages them:

```bash
git reset HEAD~1
```

### Hard reset

Deletes local changes represented by the reset:

```bash
git reset --hard HEAD~1
```

**Warning:** `--hard` can permanently remove uncommitted work.

---

# 44. Git Revert

For a commit that has already been shared, prefer:

```bash
git revert COMMIT_ID
```

This creates a new commit that reverses the earlier commit.

Find commit IDs:

```bash
git log --oneline
```

Example:

```bash
git revert a1b2c3d
```

---

# 45. Git Reset vs Revert

| Command | Typical use |
|---|---|
| `git reset` | Rewrite local branch history |
| `git revert` | Safely undo a shared commit by creating a new commit |

For team repositories, `git revert` is generally safer for undoing already-pushed changes.

---

# 46. Remote Repository Commands

Show remotes:

```bash
git remote -v
```

Add remote:

```bash
git remote add origin URL
```

Change remote URL:

```bash
git remote set-url origin URL
```

Remove remote:

```bash
git remote remove origin
```

---

# 47. Git Tags

Tags are commonly used to mark versions.

Create:

```bash
git tag v1.0.0
```

List:

```bash
git tag
```

Push:

```bash
git push origin v1.0.0
```

Push all tags:

```bash
git push origin --tags
```

---

# 48. Annotated Tag

Recommended for releases:

```bash
git tag -a v1.0.0 -m "Version 1.0.0"
```

Push:

```bash
git push origin v1.0.0
```

---

# 49. GitHub Releases

A GitHub Release can be created from a tag.

Typical versioning:

```text
v1.0.0
v1.1.0
v1.1.1
v2.0.0
```

Common meaning:

```text
MAJOR.MINOR.PATCH
```

Example:

```text
1.2.3
```

- `1` = major version
- `2` = minor version
- `3` = patch version

---

# 50. GitHub Issues

Issues are used to track:

- Bugs
- Features
- Tasks
- Improvements
- Questions

Example:

```text
Issue #25
Title: Login button not working

Description:
The login button does not submit the form.

Expected:
User should be redirected to dashboard.
```

---

# 51. GitHub Fork

Forking creates a copy of another user's repository under your GitHub account.

Common open-source workflow:

```text
Original Repository
        |
       Fork
        |
        v
Your GitHub Repository
        |
       Clone
        |
        v
Local Computer
        |
      Changes
        |
        v
Your GitHub
        |
 Pull Request
        |
        v
Original Repository
```

---

# 52. GitHub SSH Authentication

SSH avoids repeatedly entering HTTPS credentials.

Generate an SSH key:

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

Press Enter to accept the default location.

Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

Add the key:

```bash
ssh-add ~/.ssh/id_ed25519
```

Display the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the public key.

GitHub:

```text
Settings
→ SSH and GPG keys
→ New SSH key
```

Paste the public key.

Test:

```bash
ssh -T git@github.com
```

---

# 53. Use SSH Repository URL

Instead of:

```text
https://github.com/USERNAME/REPOSITORY.git
```

Use:

```text
git@github.com:USERNAME/REPOSITORY.git
```

Clone:

```bash
git clone git@github.com:USERNAME/REPOSITORY.git
```

Change an existing repository:

```bash
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

---

# 54. GitHub Personal Access Token

For HTTPS authentication, GitHub does not use your normal account password for Git operations.

If authentication requires a token, create a Personal Access Token from GitHub settings and use it according to GitHub's current authentication options.

Do not put tokens directly into repository URLs or source code.

---

# 55. GitHub Repository Visibility

Repositories can generally be:

### Public

Anyone can view the repository.

### Private

Only authorized users can access it.

Choose the visibility based on the project and organization requirements.

---

# 56. README.md

A good repository should normally contain a README.

Example:

```markdown
# My Application

## Description

A simple web application.

## Features

- User registration
- Login
- Dashboard

## Installation

```bash
npm install
```

## Run

```bash
npm run dev
```

## Build

```bash
npm run build
```

## Technologies

- React
- Node.js
- PostgreSQL
```

---

# 57. GitHub Repository Structure

Example:

```text
my-project/
│
├── .git/
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── src/
├── public/
├── tests/
│
├── .gitignore
├── README.md
├── package.json
└── LICENSE
```

---

# 58. GitHub Actions

GitHub Actions provides CI/CD automation.

Example workflow:

```text
Developer
   |
   v
git push
   |
   v
GitHub
   |
   v
GitHub Actions
   |
   +---- Install dependencies
   |
   +---- Run tests
   |
   +---- Build
   |
   +---- Deploy
```

---

# 59. Basic GitHub Actions Workflow

Create:

```text
.github/workflows/ci.yml
```

Example:

```yaml
name: Node CI

on:
  push:
    branches:
      - main

  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20

      - name: Install dependencies
        run: npm ci

      - name: Build
        run: npm run build
```

The exact Node.js version should match the project's supported version.

---

# 60. GitHub Actions Secrets

Never put passwords or cloud credentials directly into workflow files.

Use:

```text
Repository
→ Settings
→ Secrets and variables
→ Actions
```

Example:

```yaml
env:
  AWS_REGION: ${{ secrets.AWS_REGION }}
```

Secrets should be managed through GitHub's secret-management features and appropriate cloud identity mechanisms.

---

# 61. GitHub Pages

GitHub Pages can host static websites.

Typical projects:

- HTML
- CSS
- JavaScript
- Static React/Vite builds with appropriate configuration

A common workflow is:

```text
Code
 |
 v
GitHub
 |
 v
GitHub Actions
 |
 v
Build
 |
 v
GitHub Pages
```

---

# 62. GitHub Organization

Organizations are useful for companies and teams.

Example:

```text
Company Organization
│
├── frontend-project
├── backend-project
├── mobile-project
├── infrastructure
└── documentation
```

Organizations can manage:

- Members
- Teams
- Repository permissions
- Projects
- Policies

---

# 63. Collaborator Access

Repository access can be controlled using permissions.

Typical levels include:

- Read
- Triage
- Write
- Maintain
- Admin

Give users only the access they need.

---

# 64. Protected Main Branch

For production repositories, protect the `main` branch.

Common rules:

- Require Pull Requests
- Require approvals
- Require successful CI checks
- Prevent direct pushes
- Prevent force pushes

Typical workflow:

```text
Developer
   |
feature branch
   |
Pull Request
   |
CI Tests
   |
Code Review
   |
Approval
   |
Merge
   |
main
```

---

# 65. Useful Git Commands

## Repository

```bash
git init
git clone URL
git status
```

## Staging

```bash
git add .
git add filename
```

## Commit

```bash
git commit -m "message"
```

## Remote

```bash
git remote -v
git remote add origin URL
```

## Push

```bash
git push
git push -u origin main
```

## Pull

```bash
git pull
```

## Fetch

```bash
git fetch
```

## Branch

```bash
git branch
git switch -c feature-name
git switch main
```

## Merge

```bash
git merge branch-name
```

## History

```bash
git log --oneline
git log --oneline --graph --decorate --all
```

## Difference

```bash
git diff
git diff --staged
```

---

# 66. Complete Real-World Example

Suppose you are developing a website.

## Step 1 — Clone

```bash
git clone git@github.com:USERNAME/my-website.git
cd my-website
```

## Step 2 — Update main

```bash
git switch main
git pull
```

## Step 3 — Create feature branch

```bash
git switch -c feature/contact-page
```

## Step 4 — Develop

Create:

```text
src/contact.html
```

or modify your application files.

## Step 5 — Check

```bash
git status
```

## Step 6 — Review changes

```bash
git diff
```

## Step 7 — Stage

```bash
git add .
```

## Step 8 — Commit

```bash
git commit -m "Add contact page"
```

## Step 9 — Push

```bash
git push -u origin feature/contact-page
```

## Step 10 — Pull Request

Open GitHub and create:

```text
feature/contact-page
        ↓
      main
```

## Step 11 — Review

Team members review the code.

## Step 12 — Merge

Merge the Pull Request.

## Step 13 — Update local main

```bash
git switch main
git pull
```

---

# 67. Recommended Branch Strategy

For a small team:

```text
main
 |
 +---- feature/login
 |
 +---- feature/payment
 |
 +---- feature/dashboard
```

For larger projects, teams may use additional branches such as:

```text
main
develop
feature/*
release/*
hotfix/*
```

The exact strategy should be agreed upon by the development team.

---

# 68. Good Commit Messages

Good:

```text
Add user login
Fix payment validation
Update AWS deployment workflow
Add product search
Fix mobile navigation
```

Avoid:

```text
update
changes
test
asdf
final
final2
new
```

A commit message should explain what changed.

---

# 69. Git Workflow Cheat Sheet

```bash
# Check status
git status

# Get latest changes
git pull

# Create branch
git switch -c feature-name

# Make changes

# Review changes
git diff

# Stage
git add .

# Commit
git commit -m "Describe changes"

# Push
git push -u origin feature-name

# After Pull Request is merged
git switch main
git pull
```

---

# 70. Troubleshooting

## Problem: git command not found

Check:

```bash
git --version
```

Install Git.

---

## Problem: Push rejected

First update your branch:

```bash
git pull
```

Resolve conflicts if required.

Then:

```bash
git push
```

---

## Problem: Authentication failed

Check:

```bash
git remote -v
```

For HTTPS, verify your GitHub authentication/token setup.

For SSH:

```bash
ssh -T git@github.com
```

---

## Problem: Wrong remote URL

Check:

```bash
git remote -v
```

Change:

```bash
git remote set-url origin NEW_URL
```

---

## Problem: Merge conflict

Check:

```bash
git status
```

Open the conflicting files.

Remove conflict markers:

```text
<<<<<<<
=======
>>>>>>>
```

Keep the correct code.

Then:

```bash
git add .
git commit -m "Resolve merge conflict"
```

---

# 71. Important Difference: Git vs GitHub

```text
Git
 |
 +-- Installed on your computer
 +-- Tracks code changes
 +-- Creates commits
 +-- Creates branches
 +-- Works offline

GitHub
 |
 +-- Cloud platform
 +-- Hosts repositories
 +-- Pull Requests
 +-- Issues
 +-- Actions
 +-- Code Reviews
 +-- Releases
 +-- Collaboration
```

---

# 72. Recommended Professional Workflow

```text
                 GitHub
                   |
                main
                   |
            Pull Request
                   |
             Code Review
                   |
              CI / Tests
                   |
                 Merge
                   |
                main
                   ^
                   |
              feature/*
                   ^
                   |
              Developer
```

Developer workflow:

```bash
git switch main
git pull

git switch -c feature/my-feature

# Write code

git status
git diff

git add .
git commit -m "Implement my feature"

git push -u origin feature/my-feature
```

Then:

```text
GitHub
→ Pull Request
→ Review
→ CI
→ Approval
→ Merge
```

Finally:

```bash
git switch main
git pull
```

---

# 73. Final Git + GitHub Checklist

Before pushing:

- [ ] Code works
- [ ] `git status` checked
- [ ] No secrets committed
- [ ] `.env` ignored
- [ ] `node_modules` ignored
- [ ] Changes reviewed with `git diff`
- [ ] Meaningful commit message used
- [ ] Correct branch selected
- [ ] Tests passed
- [ ] Build passed

Before merging:

- [ ] Pull Request created
- [ ] Description added
- [ ] CI passed
- [ ] Code reviewed
- [ ] Conflicts resolved
- [ ] Required approvals obtained

---

# 74. Practice Project

Create a simple project:

```text
github-practice/
├── index.html
├── style.css
├── script.js
├── README.md
└── .gitignore
```

Initialize:

```bash
git init
```

Create first commit:

```bash
git add .
git commit -m "Initial project"
```

Create GitHub repository.

Connect:

```bash
git remote add origin git@github.com:USERNAME/github-practice.git
```

Push:

```bash
git branch -M main
git push -u origin main
```

Create a feature:

```bash
git switch -c feature/home-page
```

Modify the website.

Then:

```bash
git add .
git commit -m "Create home page"
git push -u origin feature/home-page
```

Create a Pull Request.

Review and merge it.

Then:

```bash
git switch main
git pull
```

---

# 75. End-to-End GitHub Learning Path

Learn in this order:

```text
1. Git installation
       ↓
2. git config
       ↓
3. git init
       ↓
4. git status
       ↓
5. git add
       ↓
6. git commit
       ↓
7. GitHub repository
       ↓
8. git remote
       ↓
9. git push
       ↓
10. git clone
       ↓
11. git pull
       ↓
12. Branches
       ↓
13. Merge
       ↓
14. Pull Requests
       ↓
15. Merge Conflicts
       ↓
16. .gitignore
       ↓
17. Tags & Releases
       ↓
18. SSH
       ↓
19. Issues
       ↓
20. GitHub Actions
       ↓
21. CI/CD
       ↓
22. Team Collaboration
```

---

# 76. One-Line Memory Trick

Remember:

```text
CLONE → BRANCH → CODE → ADD → COMMIT → PUSH → PR → REVIEW → MERGE → PULL
```

For a new local project:

```text
INIT → ADD → COMMIT → REMOTE → PUSH
```

---

# 77. Most Important Commands to Remember

```bash
git init
git clone URL

git status

git add .
git commit -m "message"

git branch
git switch -c feature-name
git switch main

git pull
git fetch

git merge branch-name

git push
git push -u origin branch-name

git remote -v

git log --oneline
git diff

git tag
git revert COMMIT_ID
```

---

# End

This guide covers the complete practical Git and GitHub workflow from creating the first repository to professional team collaboration and basic CI/CD.
