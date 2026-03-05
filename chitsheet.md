- This git command shows the current branch status, including staged, unstaged, and untracked files.
    - `git status`
---

- This stages a specific file or file path for the next commit.
    - `git add (filename or <file path>)`
---

- This stages all changes at once, including new, modified, and deleted files.
    - `git add -A`
---

- This creates a commit from staged changes and opens the commit message editor.
    - `git commit`
        - `i` : Enters insert mode in Vim so you can type the commit message.
        - `esc + : + w + q` : Saves and quits Vim to complete the commit.
---

- This creates a new empty file. If it already exists, it updates the timestamp.
    - `touch <filename>`
---

- This command is used to switch branches or restore files when used with arguments.
    - `git checkout <branchname>`
---

- This force checkout discards conflicting local changes for the checkout target.
    - `git checkout -f`
---

- This shows the commit history of your repository.
    - `git log`
---

- This shows detailed patch output for the last N commits.
    - `git log -p -n <number of commits>`
---

- This shows unstaged changes between working directory and staging area.
    - `git diff`
---

- This shows only the staged changes that will go in the next commit.
    - `git diff --staged`
---

- This commits tracked changed files directly with a commit message.
    - `git commit -a -m "message"`
---

- This removes a file from Git and stages the deletion.
    - `git rm <filename>`
---

- This removes a file from Git tracking but keeps the local file.
    - `git rm --cached <filename>`
---

- This gives a short and compact status output.
    - `git status -s`
---

- This file stores ignore rules so Git skips matching files and folders.
    - `.gitignore`
    - `/mylogs.log` : Ignores only this root-level file named `mylogs.log`.
    - `*.log` : Ignores all files ending with `.log`.
    - `<foldername>/` : Ignores the full folder and everything inside it.
---

- This creates a new branch from your current commit.
    - `git branch <branchname>`
---

- This switches your working directory to an existing branch.
    - `git checkout <branchname>`
---

- This merges another branch into your current branch.
    - `git merge <branchname>`
---

- This creates a new branch and switches to it immediately.
    - `git checkout -b <branchname>`
---

- This temporarily saves uncommitted changes so you can switch context safely.
    - `git stash`
---

- This exports installed Python packages to a clean requirements file.
    - `pip list --format=freeze > requirements_clean.txt`
---

- This initializes a new Git repository in the current folder.
    - `git init`
---

- This downloads an existing remote repository to your local machine.
    - `git clone <repo-url>`
---

- This sets your global Git username used in commits.
    - `git config --global user.name "Your Name"`
---

- This sets your global Git email used in commits.
    - `git config --global user.email "you@example.com"`
---

- This lists remote names and their fetch and push URLs.
    - `git remote -v`
---

- This adds a remote named `origin` pointing to your repository URL.
    - `git remote add origin <repo-url>`
---

- This downloads all remote updates and removes stale remote-tracking branches.
    - `git fetch --all --prune`
---

- This fetches and merges updates from a remote branch into the current branch.
    - `git pull origin <branchname>`
---

- This pushes your current branch commits to the remote branch.
    - `git push origin <branchname>`
---

- This switches to an existing branch using modern Git syntax.
    - `git switch <branchname>`
---

- This creates a new branch and switches to it using modern syntax.
    - `git switch -c <branchname>`
---

- This restores a file in working directory to its last committed state.
    - `git restore <filename>`
---

- This unstages a file but keeps its working directory changes.
    - `git restore --staged <filename>`
---

- This shows all currently saved stashes.
    - `git stash list`
---

- This reapplies the latest stash and removes it from stash list.
    - `git stash pop`
---

- This creates a new commit that safely undoes a specific commit.
    - `git revert <commit-hash>`
---

- This moves HEAD back one commit but keeps all changes staged.
    - `git reset --soft HEAD~1`
---

- This reapplies your commits on top of another base branch.
    - `git rebase <branchname>`
---

- This applies a specific commit from another branch to current branch.
    - `git cherry-pick <commit-hash>`
---

- This creates a lightweight tag for a specific release point.
    - `git tag <tagname>`
---

- This creates an annotated tag with message and metadata.
    - `git tag -a <tagname> -m "message"`
---

- This pushes a specific tag to remote.
    - `git push origin <tagname>`
---

- This shows detailed information for a specific commit or tag.
    - `git show <commit-hash>`
---

- This pushes your branch and sets upstream so future push/pull can be shorter.
    - `git push -u origin <branchname>`
---

- This deletes a local branch only if it is already merged.
    - `git branch -d <branchname>`
---

- This force deletes a local branch even if it is not merged.
    - `git branch -D <branchname>`
---

- This reapplies stashed changes but keeps that stash entry in the stash list.
    - `git stash apply`
---

- This deletes a specific stash entry after you no longer need it.
    - `git stash drop`
---

- This shows a compact commit history graph across all branches.
    - `git log --oneline --graph --all`
---

- This shows where HEAD and branch references pointed in recent actions.
    - `git reflog`
---

- This updates the last commit message (or content if staged changes exist).
    - `git commit --amend -m "new message"`
---

- This removes untracked files and folders from working directory, so use with care.
    - `git clean -fd`
---

- This resets branch and working tree to a commit and discards local changes.
    - `git reset --hard <commit-hash>`
---

- This renames the current branch (or an old name when provided).
    - `git branch -m <new-name>`
    - `git branch -m <old-name> <new-name>`
---

- This merges another branch but always creates a merge commit (no fast‑forward).
    - `git merge --no-ff <branchname>`
---

- This pulls from remote and rebases local commits on top instead of merging.
    - `git pull --rebase origin <branchname>`
---

- This shows who last modified each line of a file.
    - `git blame <file>`
---

- This searches for a pattern in the repository.
    - `git grep <pattern>`
---

- This helps find the commit that introduced a bug by binary search.
    - `git bisect start`
    - `git bisect good <commit>`
    - `git bisect bad <commit>`
---

- These commands manage submodules (if your project uses them).
    - `git submodule add <repo> [path]`
    - `git submodule init`
    - `git submodule update`
---
