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

1. Initiation

- `git init` - create

2. Add files to Index

- `git add .` - add all current files
- `git add [file]` - add this file only
- `git add *.c` - add all files with .c extension

1. First Commit
-`git commit -m "Initial commit"`

### Clone

- Use Githab.com <https://github.com/makeevstranik/git-practice>
- Use *code* button in definite rep which should be cloned to take the url
- Clone and create the same folder
`git clone https://github.com/makeevstranik/git-practice.git`
- Clone and create other folder
`git clone https://github.com/makeevstranik/git-practice.git newFolderName`
