# Day 2: The Core Workflow (Add, Commit, Log)

## 1. Concept: Snapshots vs Deltas
Git thinks of its data like a series of snapshots of a miniature filesystem. Every time you commit, Git takes a picture of what all your files look like at that moment and stores a reference to that snapshot.

## 2. Checking Status (`git status`)
The most important command. It tells you:
- Which files are modified.
- Which files are staged.
- Which files are untracked.

## 3. Staging Changes (`git add`)
Moves changes from **Working Directory** to **Staging Area**.
- **Add specific file**: `git add filename.txt`
- **Add everything**: `git add .`

## 4. Saving Changes (`git commit`)
Moves changes from **Staging Area** to **Repository**.
- **Syntax**: `git commit -m "Descriptive message"`
- **Why**: A commit is a permanent checkpoint.
- **Best Practice**: Write clear, imperative messages (e.g., "Fix login bug" not "Fixed bug").

## 5. Viewing History (`git log`)
- `git log`: Show full history.
- `git log --oneline`: Compact view (Hash + Message).
- `git log -p`: Show the actual changes (diffs) in each commit.

## 6. Exercises
1.  Inside `git_practice`, create `file1.txt` with text "Version 1".
2.  Run `git status` (See it's untracked).
3.  Run `git add file1.txt`.
4.  Run `git status` (See it's ready to be committed).
5.  Run `git commit -m "Initial commit"`.
6.  Modify `file1.txt` to "Version 2".
7.  Add and commit it.
8.  Run `git log --oneline`.

## 7. Interview Question
**Q: What is the Staging Area (or Index) and why is it useful?**
*A: The Staging Area is an intermediate layer between the working directory and the repository. It allows developers to selectively pick which changes to include in the next commit, rather than committing all modified files at once. This enables atomic, logical commits.*
