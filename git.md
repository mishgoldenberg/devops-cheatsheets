# Git cheat sheet

The answers from every Git quiz on [@mish.builds](https://www.instagram.com/mish.builds/), plus the one line that explains each.

## Everyday

| Task | Command | Why |
|---|---|---|
| New branch and switch to it | `git switch -c feat` | Older form: `git checkout -b feat`. |
| See unstaged changes | `git diff` | `git diff --staged` = what will be committed. |
| Download, touch nothing | `git fetch` | Only updates remote branches. pull = fetch + merge. |
| Pull without a merge commit | `git pull --rebase` | Replays your commits on top of the remote. |
| Park unfinished work | `git stash` | `git stash pop` brings it back. |
| Never track node_modules | `.gitignore` | Lists paths Git leaves untracked. |

## Undo (safe → dangerous)

| Task | Command | Why |
|---|---|---|
| Unstage, keep edits | `git restore --staged file` | Only touches the index. |
| Fix last commit message | `git commit --amend` | Rewrites the last commit. Only before you push. |
| Undo last commit, keep changes | `git reset --soft HEAD~1` | Moves the branch back. Changes stay staged. |
| Undo on a shared branch | `git revert <sha>` | Adds a new commit that undoes the old one. History stays. |
| ⚠ Throws away uncommitted work | `git reset --hard` | Overwrites tracked files. No undo. |
| Lost a commit after a bad reset | `git reflog` | Records every place HEAD has been. |

## Detective work

| Task | Command | Why |
|---|---|---|
| Who changed each line | `git blame file` | Commit and author of every line. |
| Which commit broke it | `git bisect` | Binary search: you answer good or bad. |
| Copy one commit here | `git cherry-pick <sha>` | Applies just that commit as a new one. |
| Branches already merged | `git branch --merged` | Safe to delete those. |

More: [Linux](linux.md) · [SQL](sql.md) · [Bash](bash.md)
