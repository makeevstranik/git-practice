# Bash practice from ios bootcamp

## SHORTCUTS

- `ctrl a` - Go to the beginning of the line you are currently typing on.
- `ctrl e` - Go to the end of the line you are currently typing on.
- `ctrl l` - Clears the Screen
- `cmd k`  - Clears the Screen
- `ctrl u` - Cut everything backwards to beginning of line
- `ctrl k` - Cut everything forward to end of line
- `ctrl w` - Cut one word backwards using white space as delimiter
- `ctrl y` - Paste whatever was cut by the last cut command
- `ctrl h` - Same as backspace
- `ctrl c` - Kill whatever you are running. Also clears everything on current line
- `ctrl d` - it the current shell when no process is running, or send EOF to a the running process
- `ctrl z` - Puts whatever is running into a suspended background process. fg restores it.
- `ctrl _` - Undo the last command.
- `ctrl t` - Swap the last two characters before the cursor
- `ctrl f` - Move cursor one character forward
- `ctrl b` - Move cursor one character backward
- `option ->` - Move cursor one word forward
- `option <-` - Move cursor one word backward
- `esc t` - Swap the last two words before the cursor
- `esc backspace` - Cut one word backwards using none alphabetic characters as delimiters
- `tab` - Auto-complete files and folder names

## CORE COMMANDS

- `cd` - Home directory
- `cd name` - name directory
- `cd ~` - Home directory
- `cd /` - Root of drive
- `cd  -` - Previous directory
- `ls` - Short listing
- `ls -l` - Long listing
- `ls -a` - Listing incl. hidden files
- `ls -lh` - Long listing with Human readable file sizes
- `ls -r` - Entire content of folder recursively
- `sudo command` - Run command with the security privileges of the superuser (Super User DO)
- `open filename` - Opens a file ( as if you double clicked it )
- `top` - Displays active processes. Press q to quit
- `open -a editorname filename` - Opens the file using this editor
- `reset` - Resets the terminal display

## CHAINING COMMANDS

- `commandA; commandB` - Run command A and then B, regardless of success of A
- `commandA && commandB` - Run command B if A succeeded
- `commandA || commandB` - Run command B if A failed
- `commandA &` - Run command A in background

## PIPING COMMANDS

- `commandA | commandB` Run command A and then pass the result to command B

## COMMAND HISTORY

- `history n` - Shows the stuff typed – add a number to limit the last n items
- `ctrl r` - Interactively search through previously typed commands
- `![value]` - Execute the last command typed that starts with ‘value’
- `![value]:p` - Print to the console the last command typed that starts with ‘value’
- `!!` - Execute the last command typed
- `!!:p` - Print to the console the last command typed
  
## FILE MANAGEMENT

- `touch filename` - Create a new file
- `pwd` - Full path to working directory
- `.` - Current folder, e.g. ls .
- `..` - Parent/enclosing directory, e.g. ls ..
- `ls -l ..` - Long listing of parent directory
- `cd ../../` - Move 2 levels up
- `cat` - Concatenate to screen
- `rm [file]` - Remove a file, e.g. rm data.tmp
- `rm *` - remove all files
- `rm -i [file]` - Remove with confirmation
- `rm -r [dir]` - Remove a directory and contents
- `rm -f [file]` - Force removal without confirmation
- `cp [file] [newfile]` - Copy file to file
- `cp [file] [dir]` - Copy file to directory
- `mv [file] [new filename]` - Move/Rename, e.g. mv file1.ad /tmp
- `pbcopy < [file]` - Move/Rename, e.g. mv file1.ad /tmp
- `pbpaste` - Paste clipboard contents
- `pbpaste > [file]` - Paste clipboard contents into file, pbpaste > paste-test.txt

## DIRECTORY MANAGEMENT

- `mkdir [dir]` - Create new directory
- `mkdir -p [dir]/[dir]` - Create nested directories
- `rmdir [dir]` - Remove directory ( only operates on empty directories )
- `rm -R [dir]` - Remove directory and contents
- `less [file]` - Output file content delivered in screensize chunks
- `[command] > [file]` - Push output to file, keep in mind it will get overwritten
- `[command] >> [file]` - Append output to existing file
- `[command] < [file]` - Tell command to read content from a file

## SEARCH

- `find [dir] -name [search_pattern]` - Search for files, e.g. find /Users -name "file.txt"
- `grep [search_pattern] [file]` - Search for all lines that contain the pattern, e.g. grep "Tom" file.txt
- `grep -r [search_pattern] [dir]` - Recursively search in all files in specified directory for all lines that contain the pattern
- `grep -v [search_pattern] [file]` - Search for all lines that do NOT contain the pattern
- `grep -i [search_pattern] [file]` - Search for all lines that contain the case-insensitive pattern
- `mdfind [search_pattern]` - Spotlight search for files (names, content, other metadata), e.g. mdfind skateboard
- `mdfind -onlyin [dir] -name [pattern]` - Spotlight search for files named like pattern in the given directory

## HELP

- `[command] -h` - Offers help for this command
- `info [command]` - Offers help
- `info [command]` - Offers help
- `man [command]` - Show the help manual for [command]
- `whatis [command]` - Gives a one-line description of [command]
- `apropos [search-pattern]` - Searches for command with keywords in description

`emacs -batch -l dunnet` - play game.  

[bash command tutor](https://www.learnenough.com/command-line-tutorial/basics)
[Git Cheatsheet](https://github.com/0nn0/git-basics-cheatsheet)