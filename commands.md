# Git Commands

## Introduction

check version: `git --version`

### Help

- `git help [command]` (`/ anyword` search, `n` next page, `[shift]n` prev page, `q` exit)
- `git [command] --help`
- `man git-[command]`
- `git [command] -h` - short info

#### example

`git help config`

### First Config

look file *.config*

- system config for all users and all rep.: `git config --system`
- for current user, all rep.: `git config --global`
- for current rep.: `git config` or `git config --local`

#### Show configs

look at configs - where and what is done
`git config --list --show-origin`

#### Change configs

for all rep.:

- users name `git config --global user.name "Makeev Evgeny"`  
- email `git config --global user.email makeevstranig@gmail.com`
for current rep if it needs:
- `git config user.name "Gena Bookin"`

change default (*master*) branch name to *main* **DON'T USE IT!**
`git config --global init.defaultBranch main`

#### Check configs

- all configs: `git config --list`
- definite config key: `git config user.name`

## Git Basics

### Creation

1 Initiation

- `git init` - create

2 Add files to Index

- `git add .` - add all current files
- `git add file_name` - add this file only
- `git add *.c` - add all files with .c extension
  
3 Exclude file from index 

- `git reset HEAD file_name` - unstage *file_name*
- `git restore --staged file_name` - the same command

4 First Commit
-`git commit -m "Initial commit"`

### Clone

- Use Githab.com <https://github.com/makeevstranik/git-practice>
- Use *code* button in definite rep which should be cloned to take the url
- Clone and create the same folder
`git clone https://github.com/makeevstranik/git-practice.git`
- Clone and create other folder
`git clone https://github.com/makeevstranik/git-practice.git newFolderName`

### Add new file

- watch status `git status` or short view `git status -s`
- add new files `git add modifiedFileName` or for all files `git add .`

### Ignore files

- create gitignore `cat .gitignore`

#### ignore example

- `man gitignore` - watch helpgit 
- `*.[oa]` ignore all files ending with *o* or *a*
- `*~` ignore all files ending with ~
- `# this is a comment in gitignore`
- `*.txt` ignore all txt files,
- `!important.txt` but exclude important.txt file
- `ignoreFolder/` ignore all files in *ignoreFolder*
- `that is a simple`
- [github swift gitignoe](https://github.com/github/gitignore/blob/main/Swift.gitignore)

### Watch staged changes

- what is changed but not staged :  `git diff`
- what is staged and is about to commit: `git diff --staged`
- `git show [commit_hash]` - changes in commit_hash commit

### Commit

- `git commit` - open editor for comment and then commit
- `git commit -m "this is my comment"` - commit whit comment
- `git commit -a -m "i did not add before this commit!"`commit all watching files without *add* command
- `git commit --author='Name <email> --date='01.01.2001'` change Author of commit

### Checkout

- `git checkout [hash_commit]` - moove HEAD to commit (but not reset!) 
  
### Delete file from git watching

- Full delete a file from git watching and from memory: `git rm fileName`
- the same but if that file is already staged: `git rm -f stagedFileName`
- the same with whole folder: `git rm folderName/\*.log`
- delete a file from git watching but not from memory: `git rm --cached fileName`
- delete git from project: `rm -rf .git*`

### Commit history

- `git log` shows all commit history

  - `git log --since=2.weeks` the same only since 2 weeks
  - `git log --since="2021-12-20"`
  - `git log --before="2020-12-12"`
  - `git log --since="5 day"`

- `git log -p -2` shows all commits with changes (2 maximum)
- `git log --stat` shows all commits with short info
- `git log --pretty=oneline` the same using 1 line for one commit
- `git log --graph` graph for commits and branches
- `git log --grep "only this message"`  shows commits with definite message

### Cancel changes

- `git commit -m "this commit will be changed"`  current commit
- `git add forgotten_file` - add forgotten file
- `git commit --amend` - cancel current commit by adding new file there
- `git checkout -- file_notToBeSaved` - **Before commit!** cancel all changes in file
- `git restore file_notToBeSaved` - the same command

### Recover git state

- `git reset --hard [commit_hash]` - moove HEAD to this commit delete(hide) all commits after it
- `git reflog` - show git state log (press 🔲 q)
- `git reset HEAD@{CHOOSE_COMMIT} --hard` recover state to this commit
- `git reset --hard ORIG_HEAD` cancel last *reset* (recover all commits) and moove HEAD to previous stage

### Remote rep

1 look at remote rep:

- `git remote` 
- `git remote -v` - show remote with address

2 add remote:

- `git remote add short_name [url]` - add remote rep from url

3 get changes from remote:
  
- `git fetch name_rep` - get changes but not merge (as *pull*)
- `git pull` - get changes and merge them

4 send changes to remote:

- `git push` - send branch *master* to rep *origin* (default for cloned rep)
- `git push remote_name branch_name` - send any rep 

5 show remote

- `git remote show origin` - show default remote rep

6 delete and rename

- `git remote rename old_short_name new_short_name` - rename rep
- `git remote remove name_rep` - delete rep

### Tags

#### show

- `git tag` show all tags
- `git tag --l "v1.*"` show all tags having *v1.*

#### create

- `git tag -a tag_label -m "message_for_tag"` - create annotated tag *tag_label* with message (tag also automatically has hash, name, email) - **using for adding meta info to commit**
- `git tag tag_label` - create light tag with *tag_label* only - **using for simple commit search**

#### tag any previous commits

1 `git log --pretty=oneline` - show commits  
2 `git tag -a 9fceb02 -m "message"` - tag commit with hash 9fceb02 (just several first symbols are enough)

#### send to remote

**push doesn't sends tags to remote!**

- `git push origin tag_name` send to *origin* tag *tag_name*
- `git push origin --tags` send all tags

#### delete

`git tag -d tag_name` - delete tag *tag_name*

---

## Git Branches

### Create new branch

**master** - default name for main branch

- `git branch ` - see current branch
- `git branch test` - create new branch **test**, but not move HEAD from **master**
- `git checkout -b test` - create new branch **test**, and move HEAD there
- `git switch -c test` - the same command
- `git log --oneline --decorate` - show HEAD pointer

### Switch branches

- `git checkout test` - switch HEAD to **test** branch
- `git switch test` - the same command
- `git log --oneline --decorate --graph -all` show graph branches story
- `git switch -` - move back to previous branch
  
### Merge branches

- `git merge test` - from main branch!!! (`git checkout master`) (or other branch where the **test** is about to be merged to)
- `git branch -d test` - delete **test** branch

### Manage branches

- `git branch` - show all local branches
- `git branch --all`- show local and remote branches
- `git branch -v` - show all branches with last commit
- `git branch --merged` - show branches that were merged in current branch
- `git branch --no-megrged` - ... were not merged
  
### Rename branches

Branches that are using by other developers must't be renamed!
Be very careful renaming the main branch!

- `git branch --move old_name new_name` - rename branch locally
- `git push --set-upstream origin new_name` - then rename branch in remote rep.
- `git push origin --delete old_name` - delete old branch
  
#### Rename main branch

It'd better to think about the name of the main branch before starting a project in oder not to rename it further!

If it's inevitably needs to be done warn your colleges and follow instructions p. 195 and may the Force be with you!

## Alias for command
`git config --global alias.c anygitcommand` - creates globaly `c` as alias for  `anygitcommand`
`git c --list` - look up `c` meaning
