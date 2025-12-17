# Day 5: Advanced Git (Time Travel)

## 1. Reset (`git reset`)
Move the current branch pointer backward. **Destructive**.
- **Soft** (`--soft`): Moves HEAD back. Changes stay in Staging. Good for fixing the last commit.
- **Mixed** (`--mixed`): Moves HEAD back. Changes stay in Working Dir. (Default).
- **Hard** (`--hard`): Moves HEAD back. **Destroys** all changes. Dangerous.
- **Example**: `git reset --hard HEAD~1` (Undo last commit completely).

## 2. Revert (`git revert`)
Safe undo. Creates a *new* commit that is the exact opposite of the target commit.
- **Why**: Use this for public branches (main) so you don't rewrite history.
- **Example**: `git revert [commit_hash]`.

## 3. Rebase (`git rebase`)
Alternative to Merge. Moves your entire branch to begin at the tip of another branch.
- **Result**: Linear history (no merge commits).
- **Rule**: **Never rebase public branches** (like main). Only rebase your local feature branch before pushing.
- **Syntax**:
  ```bash
  git checkout feature
  git rebase main
  ```

## 4. Cherry-Pick (`git cherry-pick`)
Apply a specific commit from another branch to your current branch.
- **Syntax**: `git cherry-pick [commit_hash]`

## 5. Exercises
1.  Make a dummy commit.
2.  Run `git reset --soft HEAD~1`. Check `git status`. (Commit is gone, files are staged).
3.  Make a bad commit.
4.  Run `git revert HEAD`. (New commit created that undoes the bad one).
5.  Create a branch, make 2 commits. Switch to main, make 1 commit.
6.  Switch back to branch. `git rebase main`. Check `git log --oneline` (Notice the linear history).

## 6. Interview Question
**Q: When should you use `git rebase` instead of `git merge`?**
*A: Use `git rebase` on your local feature branch to keep history clean and linear before merging into the main branch. Never use it on shared public branches as it rewrites history.*
