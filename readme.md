# Git Cafe Exercise — Bundle 1 to Bundle 6

## Bundle 1

### Exercise 1

```bash
mkdir gym-git
cd gym-git
git init

git branch -M main
git add .
git commit -m "Initial project setup"

git remote add origin https://github.com/USERNAME/REPOSITORY.git
git remote -v
git push -u origin main

git switch -c dev
git switch -c test
git switch dev
git branch -d test
```

### Exercise 2

```bash
git status

git stash push -m "home page changes"

git stash push -m "about page changes"

git stash push -m "team page changes"

git stash list

git stash pop stash@{1}
git stash list
git stash pop stash@{1}

git add .
git commit -m "Add home and about pages"
git push

git stash list
git stash pop stash@{0}

git reset --hard HEAD
```

---

# Bundle 2

## Exercise 1

```bash
git switch main
git pull origin main

git switch -c ft/bundle-2

git add .
git commit -m "Add services page"

git push -u origin ft/bundle-2
```

Create PR:

```text
ft/bundle-2 -> main
```

Request review and merge the PR.

---

## Exercise 2

```bash
git switch main
git pull origin main

git switch -c ft/service-redesign

git add .
git commit -m "Redesign services page"

git push -u origin ft/service-redesign
```

Create PR:

```text
ft/service-redesign -> main
```

Then make conflicting changes on `main`:

```bash
git switch main

git add .
git commit -m "Update services page"

git push origin main
```

Go back to the feature branch:

```bash
git switch ft/service-redesign
```

Compare the branches:

```bash
git diff main..ft/service-redesign
```

Merge `main` into the feature branch:

```bash
git merge main
```

Resolve conflicts if necessary.

```bash
git add .
git commit -m "Merge main into service redesign"
git push
```

---

# Bundle 3

## Exercise 1

```bash
git switch main
git switch -c ft/team-page

git add .
git commit -m "Add team page"

git push -u origin ft/team-page
```

Create PR:

```text
ft/team-page -> main
```

Create the contact branch:

```bash
git switch main
git switch -c ft/contact-page
```

Go to the team branch:

```bash
git switch ft/team-page
git log --oneline
```

Copy the last commit hash.

Go back to contact:

```bash
git switch ft/contact-page
git cherry-pick <team-commit-hash>
```

Add contact changes:

```bash
git add .
git commit -m "Add contact page"
git push -u origin ft/contact-page
```

Create PR:

```text
ft/contact-page -> main
```

Create FAQ branch:

```bash
git switch -c ft/faq-page
```

Add `faq.html`:

```bash
git add .
git commit -m "Add FAQ page"
git push -u origin ft/faq-page
```

Revert the team-page commit:

```bash
git revert <team-commit-hash>
git push
```

Create PR:

```text
ft/faq-page -> main
```

---

## Exercise 2

```bash
git switch ft/faq-page
git switch -c ft/home-page-redesign
```

Go to main and make changes:

```bash
git switch main

git add .
git commit -m "Update home page"
git push origin main
```

Rebase the feature branch:

```bash
git switch ft/home-page-redesign
git rebase main
```

Add home page changes:

```bash
git add .
git commit -m "Redesign home page"
git push -u origin ft/home-page-redesign
```

Create PR:

```text
ft/home-page-redesign -> main
```

---

# Bundle 4

## Exercise 1

```bash
git switch main

git remote add git-copy https://github.com/USERNAME/SECOND-REPOSITORY.git
git remote -v

git add .
git commit -m "Update home page"

git push origin main
git push git-copy main
```

---

## Exercise 2

```bash
git switch main
git switch -c ft/footer

git add .
git commit -m "Add footer"

git add .
git commit -m "Improve footer"

git push -u origin ft/footer
```

Create PR:

```text
ft/footer -> main
```

Create the squashing branch:

```bash
git switch main
git switch -c ft/squashing
```

Squash the footer changes:

```bash
git merge --squash ft/footer

git add .
git commit -m "footer changes squashing"

git push -u origin ft/squashing
```

Create PR:

```text
ft/squashing -> main
```

---

# Bundle 5

## Exercise 1

### Fork and clone

```bash
git clone https://github.com/USERNAME/git-cafe-exercise.git
cd git-cafe-exercise

git remote -v
```

Edit `index.html`.

Change:

```text
Welcome to our place
```

to:

```text
Welcome to our restaurant
```

Then:

```bash
git status
git diff

git add index.html
git commit -m "Update restaurant welcome message"
git push origin main
```

Create PR:

```text
YOUR_USERNAME:main -> TheGymRwanda:main
```

---

# Bundle 6

## Exercise 1 — Menu Page

```bash
git switch main
git pull origin main

git switch -c ft/menu-page

git add menu.html index.html
git commit -m "feat: add menu page"

git push -u origin ft/menu-page
```

Create PR:

```text
ft/menu-page -> main
```

Request review.

---

## Exercise 2 — Contact Page Bug Fix

```bash
git switch main
git pull origin main

git switch -c ft/contact-page
```

Edit `index-4.html` and change the title to:

```html
<title>Contact</title>
```

Then:

```bash
git add index-4.html
git commit -m "fix: update contact page title"
git push -u origin ft/contact-page
```

Create PR:

```text
ft/contact-page -> main
```

Request review.

---

## Exercise 3 — Hotfix

```bash
git switch main
git pull origin main

git switch -c hotfix/contact-number
```

Change:

```text
+1 800 603 6035
```

to:

```text
+1 800 659 6035
```

Then:

```bash
git add .
git commit -m "fix: update contact telephone number"
git push -u origin hotfix/contact-number
```

Create PR:

```text
hotfix/contact-number -> main
```

---

## Exercise 4 — Review Peer PRs

Review the assigned PR.

Request changes when necessary.

After the author makes the required changes:

```text
Approve
```

Then merge the PR.

---

# Common Commands

```bash
git status
git branch
git switch main
git switch -c <branch-name>
git add .
git commit -m "message"
git push
git push -u origin <branch-name>
git pull origin main
git log --oneline
git diff main..<branch-name>
git merge <branch-name>
git merge --squash <branch-name>
git rebase main
git cherry-pick <commit-hash>
git revert <commit-hash>
git reset --hard HEAD
git stash
git stash list
git stash pop
git remote -v
git remote add <name> <url>
git branch -d <branch-name>
```
