# Day 6: DevOps Workflows & Best Practices

## 1. .gitignore
A file that tells Git what to ignore.
- **What to ignore**: Build artifacts (`/dist`, `/build`), Secrets (`.env`, `keys.pem`), Dependencies (`node_modules/`, `venv/`).
- **Example**:
  ```
  # Ignore logs
  *.log
  # Ignore node modules
  node_modules/
  ```

## 2. Gitflow Workflow
A strict branching model.
- **Main**: Production code.
- **Develop**: Integration branch.
- **Feature**: Branched from Develop. Merged back to Develop.
- **Release**: Branched from Develop. Merged to Main and Develop.
- **Hotfix**: Branched from Main. Merged to Main and Develop.

## 3. Trunk-Based Development
Modern DevOps standard (CI/CD friendly).
- **Trunk (Main)**: The only long-lived branch.
- **Short-lived Feature Branches**: Developers branch off Main, commit, and merge back quickly (often daily).
- **Why**: Reduces "Merge Hell".

## 4. Stashing (`git stash`)
Save uncommitted changes temporarily to switch branches.
- `git stash`: Save changes.
- `git stash pop`: Restore changes.
- `git stash list`: See saved stashes.

## 5. Exercises
1.  Create a `.gitignore` file. Add `*.tmp`.
2.  Create `file.tmp`. Run `git status`. (It should be invisible).
3.  Modify a tracked file. Run `git stash`.
4.  Switch branches, do something, switch back.
5.  Run `git stash pop`.

## 6. Interview Question
**Q: What is the difference between Gitflow and Trunk-Based Development?**
*A: Gitflow uses multiple long-lived branches (develop, release) and is good for scheduled releases. Trunk-Based Development uses a single main branch with short-lived feature branches, enabling Continuous Integration and faster delivery.*
