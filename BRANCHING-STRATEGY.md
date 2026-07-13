# BRANCHING-STRATEGY.md

## Branching Strategy

For this project, I followed the **Git Flow branching strategy** because it provides a structured workflow for managing feature development, releases, and urgent fixes. Git Flow separates stable production code from ongoing development work, making it suitable for projects where multiple features and fixes are developed simultaneously.

## Branch Diagram

```
                         feature/add-navigation
                        /
main ------------------●----------------------●
        \                                  /
         \                                /
          develop -----------------------●
                    \
                     \
                      feature/add-footer
                       \
                        ●

main
 |
 |------ hotfix/urgent-fix
              |
              ●
              |
              merge back to main
```

## Branch Rules

### Main Branch

* `main` contains stable and production-ready code.
* Direct commits to `main` are avoided.
* Changes are merged through Pull Requests after review and approval.

### Develop Branch

* `develop` is used as the integration branch for completed features.
* Feature branches are created from `develop`.
* After testing, changes are merged back into `develop`.

### Feature Branches

* New features are developed in separate branches.
* Feature branches are created from `develop`.

Naming convention:

```
feature/<feature-name>
```

Examples:

```
feature/add-navigation
feature/add-footer
feature/add-sidebar
```

### Hotfix Branches

* Hotfix branches are created when urgent production fixes are required.
* Hotfix branches are created from `main`.

Naming convention:

```
hotfix/<issue-name>
```

Example:

```
hotfix/urgent-fix
```

## Merge vs Rebase Rules

### Merge

* Used when integrating completed features into shared branches.
* Preserves the complete branch history.
* Preferred for merging feature branches through Pull Requests.

### Rebase

* Used to update a local feature branch with the latest changes from `main` or `develop`.
* Keeps commit history clean and linear.
* Avoid rebasing branches that are already shared with other developers because it rewrites history.

## Azure DevOps Branch Policies

Azure DevOps branch policies help enforce this branching strategy by controlling how changes enter protected branches.

Policies applied to `main` include:

* Require Pull Requests before merging.
* Require at least one reviewer approval.
* Prevent direct pushes to protected branches.
* Require successful build validation before merging.
* Check for linked work items and completed reviews.

These policies ensure that only reviewed, tested, and approved changes are merged into important branches, maintaining code quality and project stability.
