
```bash
Name-Shreya Badgaiyan
Training Batch-Batch1
Date-10-07-2026
About the Project- This is a simple project built using html, css and js.



.gitignore Explanation



What happens if you forget `.gitignore` on the first commit?



If `.gitignore` is not added before the first commit, unwanted files such as IDE settings, build outputs, dependencies, and operating system-generated files may be committed and pushed to the repository. This can increase repository size, create unnecessary changes, and expose files that should not be shared.



How do you fix it retroactively?



Adding files to `.gitignore` after they have already been committed does not remove them from Git tracking. You need to remove the files from Git's index while keeping them on your computer, then commit the change.



Commands:



```bash

git rm -r --cached .

git add .

git commit -m "Add .gitignore and remove unwanted files"

git push


## Latest Main Update

Main branch received new updates before sidebar integration.


## Rebase Explanation

### When should you rebase vs merge?

Rebase is useful when you want to update a feature branch with the latest changes from main and maintain a clean, linear project history.

Merge is useful when combining completed branches and preserving the complete history of how branches were integrated.

### Golden Rule of Rebasing

Never rebase commits that have already been pushed and shared with other developers.

Rebasing rewrites commit history by creating new commit IDs. If other people are using the old history, rebasing can create confusion and require them to resolve unnecessary problems.

In this task, the feature branch was rebased before merging because it was a private development branch.

