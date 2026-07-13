# Git Recovery Documentation

## Git Revert

`git revert` should be used when undoing changes on shared branches like `main`.

It creates a **new commit** that reverses the unwanted changes while keeping the existing commit history intact. This makes it safer for collaborative projects because other developers do not need to update their local history.

Example:

```bash
git revert <commit-id>
```

---

## Git Reset

`git reset --hard` moves the branch pointer back to a previous commit and removes commits from the current branch history.

It is useful for cleaning up local changes that have not been shared. However, it should be avoided on shared branches because it rewrites history and can cause issues for developers who have already pulled those commits.

Example:

```bash
git reset --hard <commit-id>
```

---

## Recovery Using Git Reflog

`git reflog` records previous positions of the `HEAD` pointer. It helps recover commits that are no longer visible after a reset.

Steps:

```bash
git reflog
```

Find the required commit ID and restore it:

```bash
git reset --hard <commit-id>
```

---

## When to Use Revert vs Reset

| Command | When to Use |
|---|---|
| `git revert` | Use for undoing commits that are already pushed or shared. It keeps history safe by creating a new commit. |
| `git reset` | Use for local commits that have not been shared. It rewrites history and should not be used on shared branches. |

---

## Summary

`git revert` is preferred in team environments because it preserves history and avoids disrupting other developers.

`git reset` is mainly used for local cleanup where rewriting commit history is acceptable.