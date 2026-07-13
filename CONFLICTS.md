# Merge Conflict Resolution Documentation

## Merge Conflict Scenario

A merge conflict was intentionally created by modifying the same file in both the `main` branch and the `feature/add-footer` branch.

When the `feature/add-footer` branch was merged into `main`, Git detected conflicting changes because both branches had different updates in the same section of the file.

---

## Conflict Markers

Git displayed conflict markers in the affected file:

```text
<<<<<<< HEAD
Changes from main branch
=======
Changes from feature/add-footer branch
>>>>>>> feature/add-footer
```

The section between `<<<<<<< HEAD` and `=======` represents the changes from the current branch (`main`).

The section between `=======` and `>>>>>>> feature/add-footer` represents the changes from the feature branch.

---

## How the Conflict Was Resolved

The conflict was resolved manually by opening the affected file and reviewing both versions of the changes.

I selected the required code from both branches, combined the changes where necessary, and removed the conflict markers:

- `<<<<<<<`
- `=======`
- `>>>>>>>`

After resolving the file, the changes were staged and committed:

```bash
git add <file-name>
git commit -m "fix: resolve merge conflict"
```

---

## Why This Resolution Was Chosen

The resolution was chosen because it preserved the required changes from both branches without losing any functionality.

Keeping both updates ensured that the footer feature and the changes made on the `main` branch were successfully integrated into the final version.

---

## Verification

The merge was verified using:

```bash
git log --oneline --graph --all
```

The history showed the merge commit successfully combining both branches.