 ![Linux](img/linux.jpg)



## Table of contents

- [Linux Commands](#linux-commands)
  - [Managing files & directories](#managing-files--directories)
    - [Basic commands](#basic-commands)
    - [View / Edit file contents](#view--edit-file-contents)
    - [Compress & extract files](#compress--extract-files)
    - [Special file types](#special-file-types)
    - [File permission](#file-permission)
  - [File system management](#file-system-management)
  - [Process management](#process-management)
  - [Managing users, groups and the system](#managing-users-,-groups-and-the-system)
  - [I/O commands](#i/o-commands)
  - [Network](#network)
  - [Hardware support](#hardware-support)
  - [Other](#other)

# Linux commands

This section gives insight into the most important commands of Linux system. Along with the individual commands, where appropriate, 
most popular parameters are listed and a typical sample application is introduced. To learn more about the various 
commands, it is usually possible to get additional information with the ***man*** program followed by the name of the command, 
for example,` man ls`.
## Managing files & directories
### Basic commands
- `cd examlpe` -- change directory to example.
  - `cd ..` -- move up one directory,
  - `cd ../..` -- move up two directory,
  - `cd -` -- change to the previous directory,
  - `cd ~` -- change to home directory.
- `pwd` -- print the absolute path of current directory.
- `ls {OPTION}... {FILE}...` -- list directory contents.
  - Options (most popular):
    - t - sort the file by modification time,
    - 1 - display one file per line, 
    - l - display all information about files/directories,
    - d - list directories themselves, not their contents, 
    - a - do not ignore hidden files,
    - i - print the index number of each file,
    - S - sort by file size, largest first
    - --group-directories-first - group directories before files.
- `cp {OPTION}... {SOURCE}... {DIRECTORY}...`  -- copy *source(s)* to *directory*.
  - Options (most popular):
    - i - ask for permission before user overwrite the destination file,
    - r - copy the entire directory structure,
    - p - preserves the time of the last data modification and the time of the last access, the ownership 
    and the file permission-bits of each source file in the corresponding destination
    file. 
- `mv` -- move (rename) files and directories
  - `mv {OPTION}... {SOURCE} {DEST}` - rename *source* to *dest*,
  - `mv {OPTION}... {SOURCE}... {DIRECTORY}` - move *source(s)* to *directory*.
  - Options (most popular):
    - i - prompt before overwriting an existing file,
    - n - never overwrite an existing file.
- `mkdir {OPTION}... {DIRECTORY}...` -- create the *directory(ies)*, if the do not already exist.
- `rmdir {OPTION}... {DIRECTORY}...` -- remove empty *directory(ies)*.
- `rm {OPTION}... {FILE}...` -- remove *file* (by default it does not remove directories).
  - Options (most popular):
    - f - ignore non-existing files,  
    - r - remove directories and their contents,
    - i - prompt before every removal,
    - v - explain at all time what is being done.
- `install {OPTION}... {SOURCE}... {DIRECTORY}` -- copy files (often just compiled) into destination locations.
### View / Edit file contents
- `touch {OPTION}... {FILE}...`  -- change file timestamps or create empty file.
- `cat {OPTION}... {FILE}...` -- reads data from the file and gives their content as output.
  - `cat >{FILE}` - create new file with content,
  - `cat >>{FILE}` - append content to the end of file_name,
  - `cat {FILE_1} >> {FILE_2}` - append the contents of file1 to the end of file2.
  - Options (most popular):
    - n - number all output lines,
    - b - number non-empty output lines,
    - s - suppress repeated empty output lines.
- `tac {OPTION}... {FILE}...` -- write each *file* to standard output, last line first.
- `nl {OPTION}... {FILE}...` -- write each *file* to standard output, with line numbers added.
- `tail {OPTION}... {FILE}...` -- output the last part of files (by default it's 10 lines).
  - Options (most popular):
    - n nums - print the last nums lines, instead of the default 10,
    - f - output appended data as the file grows.
- `head {OPTION}... {FILE}...` -- output the first part of files (by default it's 10 lines).
  - Options (most popular):
    - n nums - print the first nums lines, instead of the default 10.
- `less {FILE}...` -- display *file* contents one page at the time.
  - Key commands (most popular):
    - space bar - move down one page,
    - b - move up one page,
    - g - go to the first line,  
    - /search_term - search forward from the current position for the search_term string,
    - ?search_term - search backward from the current position for the search_term string,
    - n - when searching, to to the next occurrence,
    - N - when searching, go to the previous occurrence.
- `od {OPTION}... {FILE}...` -- write an unambiguous representation, octal bytes by default, of 
*file* to standard output.
- `base64 {OPTION}... {FILE}` -- base64 encode or decode *file*, or standard input, to standard
output.
  - Options (most popular):
    - d - decode data
    - i - when decoding, ignore non-alphabet characters
- `fold {OPTION}... {FILE}...` -- wrap each input line to fit in specified width.
  - Options (most popular):
    - b - limit the width of the output by the number of bytes (e.x. b40)
- `gedit {OPTION...} {FILE...}` -- text editor for the GNOME Desktop.
- `sort {OPTION}... {FILE}...` -- sort lines of text files (write sorted concatenation of all 
*file(s)* to standard output).
  - Options (most popular):
    - r - sort in reverse order
    - n - sort a file numerically
    - u - sort and remove duplicates
- `test {EXPRESSION}` -- check file types and compare values (exit with the status determined by *expression*).
- `expand {OPTION}... {FILE}...` -- convert tabs to spaces.
- `unexpand {OPTION}... {FILE}...` -- convert spaces to tabs.
- `fmt {OPTION}... {FILE}...` --  simple optimal text formatter (reformat each paragraph in the *file(s)*, writing to standard output).
- `pr {OPTION}... {FILE}...` -- convert text files for printing.
- `split {OPTION}... {FILE[PREFIX]}` -- split a file into pieces.
- `csplit {OPTION}... {FILE} {PATTERN}...` -- split a file into sections determined by context lines.
- `grep {OPTION}... {PATTERN} {FILE...}` -- print lines that match patterns.
- `shuf {OPTION}... {FILE}` --  generate random permutations.
- `uniq {OPTION}... {INPUT {OUTPUT}}` -- report or omit repeated lines (filter adjacent matching lines from *input*, writting to *output*.
- `comm {OPTION}... {FILE_1} {FILE_2}` -- compare sorted files *file_1* and *file_2* line by line.
- `tsort {OPTION} {FILE}` -- perform topological sort.
- `cut {OPTION}... {FILE}...` -- remove sections from each line of files.
- `paste {OPTION}... {FILE}...` -- merge lines of files.
- `join {OPTION}... {FILE_1} {FILE_2)` -- join lines of two files on a common field.

### File summary
- `wc {OPTION}... {FILE}...` -- show information about the file: number of lines, word count, byte and characters count. 
- `sum {OPTION}... {FILE}...` -- checksum and count the blocks in a file.
- `cksum {FILE}...` -- checksum and count the bytes in a file.
- `md5sum {OPTION}... {FILE}...` -- compute and check MD5 message digest.
- `sha1sum {OPTION}... {FILE}` -- compute and check SHA1 message digest.

### Compress & extract files
WIP
### Special file types
WIP
### File permission
WIP
## File system management
Work in progress
## Process management
Work in progrss
## Managing users, groups and the system
Work in progress
## I/O commands
Work in progress
## Network
Work in progress
## Hardware support
Work in progress
## Other
Work in progress


