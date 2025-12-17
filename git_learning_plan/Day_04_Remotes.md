# Day 4: Remotes & Collaboration

## 1. Concept: Remotes
A "Remote" is just another copy of the repository, usually on a server (GitHub, GitLab, Bitbucket).
- **Origin**: The default name for the main remote server.
- **Upstream**: Often used to refer to the original repo if you forked it.

## 2. Connecting to Remotes
- **Clone**: Download a repo from a server.
  `git clone https://github.com/user/repo.git`
- **Add Remote**: Link an existing local repo to a server.
  `git remote add origin https://github.com/user/repo.git`
- **View Remotes**: `git remote -v`.

## 3. Push & Pull
- **Push**: Upload local commits to remote.
  `git push origin main`
- **Pull**: Download remote commits and merge them into local.
  `git pull origin main`
- **Fetch**: Download remote commits but DO NOT merge. Safe way to check changes.
  `git fetch origin`

## 4. Tracking Branches
Local branches usually "track" a remote branch (e.g., `main` tracks `origin/main`).
- `git push -u origin feature-login`: Pushes and sets "Upstream" tracking. Next time just type `git push`.

## 5. Exercises
(Requires a GitHub account - free).
1.  Create a new repository on GitHub (Empty).
2.  In your local `git_practice` folder:
    `git remote add origin [YOUR_REPO_URL]`
3.  Push your code: `git push -u origin main`.
4.  Go to GitHub and see your files.
5.  Edit a file on GitHub (click Pencil icon) and commit.
6.  Locally, run `git pull` to get that change.

## 6. Interview Question
**Q: What is the difference between `git fetch` and `git pull`?**
*A: `git fetch` downloads the latest commits from the remote but does not modify your working directory. `git pull` is essentially `git fetch` followed immediately by `git merge`. It downloads changes and tries to merge them into your current branch.*
