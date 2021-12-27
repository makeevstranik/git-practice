# Git Commands

## Introduction

check version: `git --version`

### Help

- `git help [command]`
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
- `git add [file]` - add this file only
- `git add *.c` - add all files with .c extension

3 First Commit
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

- `man gitignore` - watch help
- `*.[oa]` ignore all files ending with *o* or *a*
- `*~` ignore all files ending with ~
- `# this is a comment in gitignore`
- `*.txt` ignore all txt files,
- `!important.txt` but exclude important.txt file
- `ignoreFolder/` ignore all files in *ignoreFolder*
- `that is a simple`

### Watch staged changes

- what is changed but not staged :  `git diff`
- what is staged and is about to commit: `git diff --staged`

### Commit

- `git commit` - open editor for comment and then commit
- `git commit -m "this is my comment"` - commit whit comment
- `git commit -a -m "i did not add before this commit!"`commit all watching files without *add* command
  
### Delete file from git watching

- Full delete a file from git watching and from memory: `git rm fileName`
- the same but if that file is already staged: `git rm -f stagedFileName`
- the same with whole folder: `git rm folderName/\*.log`
- delete a file from git watching but not from memory: `git rm --cached fileName`

### Commit history

- `git log` shows all commit history
      * `git log --since=2.weeks` the same only since 2 weeks
      * `git log --since="2021-12-20"`
      * `git log --before="2020-12-12"`
      * `git log --since="5 day"`
-  `git log -p -2` shows all commits with changes (2 maximum)
-  `git log --stat` shows all commits with short info
-  `git log --pretty=oneline` the same using 1 line for one commit
-  `git log --graph` graph for commits and branches
-  `git log --grep "only this message"`  shows commits with definite message 