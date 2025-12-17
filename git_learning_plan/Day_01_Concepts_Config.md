# Day 1: Git Concepts, Config & Init

## 1. Concept: Version Control Systems (VCS)
Imagine writing a document. You save "Final.doc", then "Final_v2.doc", then "Final_REALLY_FINAL.doc". This is messy.
**Git** is a Distributed VCS. It records changes to a file or set of files over time so that you can recall specific versions later.

**Why use it?**
- **History**: Undo mistakes easily.
- **Collaboration**: Multiple people work on the same code without overwriting each other.
- **Safety**: Every developer has a full backup of the project history.

## 2. The Three Stages
Git is not just "Saving". It has 3 areas:
1.  **Working Directory**: Your actual files on disk (where you edit).
2.  **Staging Area (Index)**: A preparation zone where you pick what changes to save.
3.  **Repository (.git)**: The permanent database of snapshots.

## 3. Configuration (`git config`)
Tell Git who you are. This information is baked into every commit you make.

- **Syntax**: `git config --global [key] [value]`
- **Commands**:
  ```bash
  git config --global user.name "Sujit"
  git config --global user.email "sujit@example.com"
  git config --global init.defaultBranch main  # Set default branch to 'main' instead of 'master'
  ```
- **View Config**: `git config --list`

## 4. Initialization (`git init`)
Turns a regular folder into a Git repository.
- **Syntax**: `git init`
- **What it does**: Creates a hidden `.git/` folder. This folder IS the repository. If you delete it, you lose all history.

## 5. Exercises
1.  Open your terminal.
2.  Configure your name and email.
3.  Create a folder `git_practice`.
4.  Enter it: `cd git_practice`.
5.  Run `git init`.
6.  Run `ls -la` to see the `.git` directory.

## 6. Interview Question
**Q: What is the difference between `git config --global` and `git config --local`?**
*A: `--global` settings apply to all repositories on your user account (stored in `~/.gitconfig`). `--local` settings apply only to the current repository (stored in `.git/config`) and override global settings.*
