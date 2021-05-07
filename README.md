# git-commands

> Refer to the whole bunch of git commands wherever & whenever it is required.

## 1. Setting up Git configuration on your PC

Use `$ git config --global user.name "[enter-your-github-username]"` to set the name you want to associate with your commits.

Use `$ git config --global user.email "[enter-your-github-account-email]"` to set the email you want to associate with your commits.

Use `$ git config --global color.ui auto` to enable helpful colorization of command line output.

Use `$ git config --global init.defaultBranch [enter-branch-name]` to change the name of the default branch whenever a repository is initialized.

Use `$ git config --global alias.[enter-alias-name] [command-name]` to change the name of a git command and make it short as per your requirements.

Use `$ git config --list` to see the current Git configuration list.

## 2. Creating a Git repository or Cloning an existing repository

Use `$ git init` to turn an existing directory into a git repository.

Use `$ git clone [enter-HTTPS URL/SSH Key]` to clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.

## 3. Working with Git staging area

Use `$ git status` to show new or modified files in working directory that needs to be staged for your next commit.

Use `$ git status -s` to show a short status.

Use `$ git add [file-name]` to add a specific file to the staging area & use `$ git add --all`/`$ git add .` to add all the file(s) to the staging area.

Use `$ git reset [file-name]` to unstage a file while retaining the changes in working directory.

Use `$ git diff` to show the difference of what is changed but not staged.

Use `$ git diff --staged` to show difference of what is staged but not yet committed.

Use `$ git commit -m "[brief message]"` to commit your staged file(s) as a new commit entry alongwith a brief message.

Use `$ git commit -a -m "[brief message]"` to skip the staging area and directly commit your file(s).

Use `$ git rm [file-name/folder-name]` to remove the file from your working directory so you don’t see it as an untracked file the next time around.

Use `$ git rm --cached [file-name/folder-name]` to keep the file in your working tree but remove it from your staging area.

Use `$ git mv [from_file-name] [to_file-name]` to rename an existing file name to some other name.

## 4. Stashing

*Stashing takes the dirty state of your working directory — that is, your modified tracked files and staged changes — and saves it on a stack of unfinished changes that you can reapply at any time (even on a different branch).*

Use `$ git stash` to save modified and staged changes.

Use `$ git stash list` to list stack-order of stashed file changes.

Use `$ git stash pop` to write working from top of stash stack.

Use `$ git stash drop` to discard the changes from top of stash stack.

## 5. Creating, Switching & Merging branches

*Branching uses tree data structure for the branches that are created. Here **root node** is known as the **master**/**main** branch & all other nodes/leaf nodes are the other branches under the master/main branch.* 

Use `$ git branch` to list all your branches. A * will appear next to the currently active branch.

Use `$ git branch [branch-name]` to create a new branch.

Use `$ git checkout [branch-name]` to switch to another branch.

Use `$ git merge [branch-name]` to merge a specified branch with the currently active branch.

## 6. Inspect & Compare commits

*Examining logs, diffs and object information.*

Use `$ git log` to show the commit history for the currently active branch.

Use `$ git log branchB..branchA` to show the commits on branchA that are not on branchB.

Use `$ git log --follow [file]` to show the commits that changed file, even across renames.

Use `$ git log --stat -M` to show all commit logs with indication of any paths that moved.

Use `$ git diff branchB..branchA` to show the difference of what is in branchA that is not in branchB.

Use `$ git show [SHA]` to show any object in Git in human-readable format.

## 7. Push a repo to GitHub or Pull a repo from GitHub

*Retrieving updates from another repository and updating local repositories.*

Use `$ git remote add [alias] [HTTPS URL/SSH Key]` to add a Github URL as an alias, e.g. `$ git remote add origin [HTTPS URL/SSH Key]` where origin is an alias.

Use `$ git remote remove [alias]` to remove Git remote.

Use `$ git fetch [alias]` to fetch down all the branches from the mentioned Git remote.

Use `$ git merge [alias]/[branch-name]` to merge a remote branch into your current branch to bring it up to date.

Use `$ git push [alias] [branch-name]` to upload local branch commits to the remote repository branch.

Use `$ git push -u [alias] [branch-name]` to upload local branch commits initially to the remote repository branch.

Use `$ git push -f [alias] [branch-name]` to upload local branch commits forcibly to the remote repository branch.

Use `$ git pull [alias] [branch-name]` to fetch and merge remote repository branch commits to the local branch.

## 8. Rewrite history

*Rewriting branches, updating commits and clearing history.*

Use `$ git rebase [branch-name]` to apply any commits of current branch ahead of specified one.

Use `$ git reset [commit]` to undo all commits after [commit], preserving changes locally.

Use `$ git reset --hard [commit]` to clear staging area, rewrite working tree from specified commit.

## 9. Ignoring patterns

*Preventing unintentional staging or commiting of file(s).*

*Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named `.gitignore`.*

### .gitignore file example

```
# ignore all .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
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
