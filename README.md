# Git Training Project

## Project Information

**Name:** Shreya Badgaiyan  
**Training Batch:** Batch 1  
**Date:** 10-07-2026  

**About the Project:**  
This is a simple web project built using HTML, CSS, and JavaScript.

---

# .gitignore Explanation

## What happens if you forget `.gitignore` on the first commit?

If `.gitignore` is not added before the first commit, unwanted files such as IDE settings, build outputs, dependencies, and operating system-generated files may be committed and pushed to the repository.

This can increase repository size, create unnecessary changes, and expose files that should not be shared.

## How do you fix it retroactively?

Adding files to `.gitignore` after they have already been committed does not remove them from Git tracking.

To fix this, remove the files from Git's index while keeping them on the local machine, then commit the changes.

Example:

```bash
git rm --cached <file-name>
git commit -m "chore: remove unwanted tracked files"
git push
```

---

# Fast-Forward Merge Explanation

A fast-forward merge occurs when the target branch has not diverged from the source branch. Git simply moves the branch pointer forward instead of creating a separate merge commit.

If both branches contain different commits after branching, Git performs a regular merge and creates a merge commit.

---

# Rebase Explanation

## When should you rebase vs merge?

### Rebase

Rebase is useful when updating a feature branch with the latest changes from `main` while maintaining a clean and linear project history.

### Merge

Merge is useful when integrating completed branches and preserving the complete history of how changes were combined.

## Golden Rule of Rebasing

**Never rebase commits that have already been pushed and shared with other developers.**

Rebasing rewrites commit history by creating new commit IDs. If other developers are using the old history, it can create confusion and require additional conflict resolution.

In this task, the feature branch was rebased before merging because it was a private development branch.

---

# Pull Request Merge Strategies

## 1. Merge Commit (No Fast-Forward)

The first Pull Request was merged using **"Create a merge commit"**.

This method keeps all individual commits from the feature branch and creates an additional merge commit. The complete development history is preserved.

Example history:

```
main
 |
 |---- Merge commit
          |
          |---- Feature commits
```

---

## 2. Squash Merge

The second Pull Request was merged using **"Squash and merge"**.

This combines all commits from the feature branch into one single commit before adding it to `main`.

Example history:

```
main
 |
 |---- One combined feature commit
```

---

# Difference Between Merge Commit and Squash Merge

| Merge Commit | Squash Merge |
|---|---|
| Keeps all individual commits | Combines multiple commits into one |
| Preserves complete development history | Creates a cleaner main branch history |
| Adds a separate merge commit | Adds only one final commit |
| Useful when detailed history is required | Useful for keeping main branch simple |

---

# Summary

This project demonstrates Git and GitHub practices including repository setup, branching strategies, commits, merging, rebasing, cherry-picking, pull requests, conflict resolution, and recovery techniques.

Following proper Git workflows helps maintain clean history, improves collaboration, and makes project management easier for teams.