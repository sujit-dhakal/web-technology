# Day 3: Branching, Merging & Conflicts

## 1. Concept: Branching
A branch in Git is simply a lightweight movable pointer to a commit. The default branch is usually `main`.
**Why?** Develop features in isolation without breaking the main code.

## 2. Managing Branches
- **Create**: `git branch feature-login`
- **Switch**: `git checkout feature-login` OR `git switch feature-login` (Newer).
- **Create & Switch**: `git checkout -b feature-login`.
- **List**: `git branch`.
- **Delete**: `git branch -d feature-login`.

## 3. Merging
Bringing history from one branch into another.
1.  Switch to the target branch (e.g., `main`).
2.  Run `git merge feature-login`.

### Types of Merges
- **Fast-Forward**: If `main` hasn't changed since you branched off, Git just moves the pointer forward. Linear history.
- **Recursive (3-Way)**: If `main` has changed, Git creates a new "Merge Commit" joining the two histories.

## 4. Conflict Resolution
Happens when the same line in the same file is edited differently in both branches.
Git will pause and mark the file:
```
<<<<<<< HEAD
Code in main
=======
Code in feature
>>>>>>> feature-login
```
**To Fix**:
1.  Open the file.
2.  Delete the markers (`<<<`, `===`, `>>>`).
3.  Keep the code you want.
4.  Save.
5.  `git add [file]`.
6.  `git commit` (No message needed, Git provides a default).

## 5. Exercises
1.  Create a branch `new-feature`. Switch to it.
2.  Create `feature.txt`. Commit it.
3.  Switch back to `main`.
4.  Merge `new-feature` into `main`.
5.  **Force a conflict**:
    - Change line 1 of `file1.txt` in `main`. Commit.
    - Change line 1 of `file1.txt` in `new-feature` to something else. Commit.
    - Merge `new-feature` into `main`.
    - Fix the conflict.

## 6. Interview Question
**Q: What is a "Fast-Forward" merge?**
*A: A fast-forward merge happens when the target branch has not diverged from the source branch. Git simply moves the tip of the target branch to the latest commit of the source branch. No new merge commit is created.*
