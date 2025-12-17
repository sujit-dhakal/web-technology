# Day 7: Git Hooks & Automation (Mini-Project)

## 1. Concept: Git Hooks
Scripts that run automatically before or after Git events (commit, push, merge).
- **Location**: `.git/hooks/`
- **Client-Side**: `pre-commit`, `commit-msg`.
- **Server-Side**: `pre-receive`, `post-receive`.

## 2. Mini-Project: Safety Net Hook
**Goal**: Create a `pre-commit` hook that prevents you from committing if you left a "TODO" or "FIXME" in the code. This ensures you don't push unfinished code.

### Solution
1.  Navigate to your repo: `cd git_practice`.
2.  Go to hooks: `cd .git/hooks`.
3.  Create file: `nano pre-commit` (No extension).
4.  Paste this script:

```bash
#!/bin/bash

echo "Running pre-commit hook..."

# Search for "TODO" or "FIXME" in staged files
if git grep -qE "TODO|FIXME"; then
    echo "ERROR: You have 'TODO' or 'FIXME' in your code."
    echo "Please resolve them before committing."
    exit 1  # Non-zero exit blocks the commit
fi

echo "Code looks clean. Proceeding..."
exit 0
```

5.  Make it executable: `chmod +x pre-commit`.

### Test It
1.  Go back to root: `cd ../..`
2.  Create a file with an error: `echo "TODO: Fix this" > todo.txt`.
3.  Add it: `git add todo.txt`.
4.  Try to commit: `git commit -m "Test hook"`.
5.  **Result**: Git should reject the commit!
6.  Remove the line, add again, and commit. It should work.

## 3. Interview Question
**Q: Where are Git hooks stored, and do they get pushed to the remote repository?**
*A: They are stored in `.git/hooks/`. By default, they are **NOT** pushed to the remote repository. To share hooks with a team, you usually use a tool like `pre-commit` (Python framework) or commit them to a separate folder and have a setup script copy them to `.git/hooks`.*

## Conclusion
You have completed the 7-Day Git Mastery Plan!
You now understand:
- The Internal Graph (Commits, Blobs).
- Branching & Merging strategies.
- How to undo mistakes safely.
- How to automate checks with Hooks.

**Next Steps**: Learn GitHub Actions (CI/CD) to automate testing on the server side.
