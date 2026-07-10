Name-Shreya Badgaiyan
Training Batch-Batch1
Date-10-07-2026
About the Project-



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

