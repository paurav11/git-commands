# git-commands

> Refer to the whole bunch of git commands wherever & whenever it is required.

## 1. Setup Git configuration on your PC

Use `$ git config --global user.name “[sername]”` to set the name you want attached to your commit transactions.

Use `$ git config --global user.email "[valid Github account email]"` to set the email you want attached to your commit transactions.

Use `$ git config --global color.ui auto` to enable helpful colorization of command line output.

Use `$ git config --list` to see the current Git configuration list.

## 2. Create a Git repository or Clone an existing repository

Use `$ git init` to turn an existing directory into a git repository.

Use `$ git clone [HTTPS URL/SSH Key]` to Clone (download) a repository that already exists on
GitHub, including all of the files, branches, and commits.

## 3. Working with Git staging area

Use `$ git status` to show modified files in working directory, staged for your next commit.

Use `$ git add [file]` to add a file as it looks now to your next commit (stage) & use `$ git add --all`/`$ git add .` to add all files to the staging area.

Use `$ git reset [file]` to unstage a file while retaining the changes in working directory.

Use `$ git diff` to show difference of what is changed but not staged.

Use `$ git diff --staged` to show difference of what is staged but not yet committed.

Use `$ git commit -m "[descriptive message]"` to commit your staged content as a new commit snapshot.

## 4. Temporary commits

*Temporary commits use stack data structure, i.e. they store data in a LIFO manner.*

Use `$ git stash` to save modified and staged changes.

Use `$ git stash list` to list stack-order of stashed file changes.

Use `$ git stash pop` to write working from top of stash stack.

Use `$ git stash drop` to discard the changes from top of stash stack.

## 5. Branching & Merging branches

*Branching uses tree data structure for the branches that are created. Here **root node** is known as the **master** branch & all other nodes/leaf nodes are the other branches under the master branch.* 

Use `$ git branch` to list all your branches. A * will appear next to the currently active branch.

Use `$ git branch [branch-name]` to create a new branch at the current commit.

Use `$ git checkout` to switch to another branch and check it out into your working directory.

Use `$ git merge [branch-name]` to merge the specified branch’s history into the current one.

## 6. Inspect & Compare commits

*Examining logs, diffs and object information.*

Use `$ git log` to show the commit history for the currently active branch.

Use `$ git log branchB..branchA` to show the commits on branchA that are not on branchB.

Use `$ git log --follow [file]` to show the commits that changed file, even across renames.

Use `$ git diff branchB..branchA` to show the difference of what is in branchA that is not in branchB.

Use `$ git show [SHA]` to show any object in Git in human-readable format.

## 7. Push the repo to Github or Pull repo from Github

*Retrieving updates from another repository and updating local repositories.*

Use `$ git remote add [alias] [HTTPS URL]` to add a Github URL as an alias, e.g. `$ git remote add origin [HTTPS URL]` where origin is an alias.

Use `$ git remote remove [alias]` to remove Git remote.

Use `$ git fetch [alias]` to fetch down all the branches from that Git remote.

Use `$ git merge [alias]/[branch-name]` to merge a remote branch into your current branch to bring it up to date.

Use `$ git push [alias] [branch-name]` to transmit local branch commits to the remote repository branch.

Use `$ git push -u [alias] [branch-name]` to transmit local branch commits once to the remote repository branch.

Use `$ git push -f [alias] [branch-name]` to transmit local branch commits forcibly to the remote repository branch.

Use `$ git pull` to fetch and merge any commits from the tracking remote branch.

## 8. Tracking path changes

*Versioning file removes and path changes.*

Use `$ git rm [file/folder name]` to delete the file/folder from project and stage the removal for commit.

Use `$ git rm --cached [file/folder name]` to remove file/folder from the index of local repository.

Use `$ git mv [existing-path] [new-path]` to change an existing file path and stage the move.

Use `$ git log --stat -M` to show all commit logs with indication of any paths that moved.

## 9. Rewrite history

*Rewriting branches, updating commits and clearing history.*

Use `$ git rebase [branch-name]` to apply any commits of current branch ahead of specified one.

Use `$ git reset [commit]` to undo all commits after [commit], preserving changes locally.

Use `$ git reset --hard [commit]` to clear staging area, rewrite working tree from specified commit.

## 10. Ignoring patterns

*Preventing unintentional staging or commiting of files.*

*Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named `.gitignore`.*

### .gitignore file example

```
logs/
*.notes
pattern*/
```

Use `git config --global core.excludesfile [file-name]` to ignore pattern for all local repositories system wide.


## Glossary

**Git**: an open source, distributed version-control system

**GitHub**: a platform for hosting and collaborating on Git repositories

**repository**: a central location in which data is stored and managed

**commit**: a Git object, a snapshot of your entire repository compressed into a SHA

**branch**: a lightweight movable pointer to a commit

**clone**: a local version of a repository, including all commits and branches

**remote**: a common repository on GitHub that all team member use to exchange their changes

**fork**: a copy of a repository on GitHub owned by a different user

**pull request**: a place to compare and discuss the differences introduced on a branch with reviews, comments, integrated
tests, and more

**HEAD**: representing your current working directory, the HEAD pointer can be moved to different branches, tags, or commits
when using `git checkout`
