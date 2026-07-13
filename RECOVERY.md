Git Revert:
git revert should be used when undoing changes on shared branches like main. It creates a new commit that reverses the unwanted changes while keeping the existing history intact. This makes it safer for collaborative projects because other developers do not need to update their local history.

Git Reset:
git reset --hard moves the branch pointer to a previous commit and removes commits from the current branch history. It can be useful for local changes that have not been shared, but it should be avoided on shared branches because it rewrites history and can cause problems for other developers who already pulled the removed commits.

Recovery using reflog:
git reflog records previous positions of the HEAD pointer, allowing recovery of commits after a reset. By finding the required commit hash from reflog and checking out or resetting back to it, lost work can be restored.

When to use:

Use revert for undoing commits that have already been pushed or shared.
Use reset for cleaning up local commits before they are shared.