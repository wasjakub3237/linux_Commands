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

## Managing files & directories
### Basic commands
- `cd examlpe` -- change directory to example.
  - `cd ..` -- move up one directory,
  - `cd ../..` -- move up two directory,
  - `cd -` -- change to the previous directory,
  - `cd ~` -- change to home directory.
- `pwd` -- shows the name of the working directory.
- `ls {options}` -- lists information about files and directories.
  - Options (most popular):
    - t - sort the file by modification time,
    - 1 - display one file per line, 
    - l - display all information about files/directories,
    - d - list directories themselves, not their contents, 
    - a - do not ignore hidden files,
    - i - print the index number of each file,
    - S - sort by file size, largest first
    - --group-directories-first - group directories before files.
- `cp {options} source destination`  -- copy files or directories.
  - Options (most popular):
    - i - ask for permission before user overwrite the destination file,
    - r - copy the entire directory structure,
    - p - preserves the time of the last data modification and the time of the last access, the ownership 
    and the file permission-bits of each source file in the corresponding destination
    file. 
- `mv {options} source destination` -- moves and renames files and directories.
  - `mv {options} file_name1 file_name2` - rename file named file_name1 to file_name2,
  - `mv {options} file_name [file_name2...] destination` - move source file(s) to destination.
  - Options (most popular):
    - i - prompt before overwriting an existing file,
    - n - never overwrite an existing file.
- `mkdir directory_name` -- create new directory.
- `rmdir directory_name` -- remove empty directory.
- `rm {options} name` -- remove file (by default it does not remove directories).
  - Options (most popular):
    - f - ignore non-existing files,  
    - r - remove directories and their contents,
    - i - prompt before every removal,
    - v - explain at all time what is being done.
- `install {options} source destination` -- copy files (often just compiled) into destination locations.
### View / Edit file contents
- `touch file_name`  -- create empty file.
- `wc file_name` -- show information about the file: number of lines, word count, byte and characters count. 
- `cat {options} file_name` -- reads data from the file and gives their content as output.
  - `cat >file_name` - create new file with content,
  - `cat >>file_name` - append content to the end of file_name,
  - `cat file1 >> file2` - append the contents of file1 to the end of file2.
  - Options (most popular):
    - n - number all output lines,
    - b - number non-empty output lines,
    - s - suppress repeated empty output lines.
- `tac {options} file_name` -- concatenate and print files in reverse.
- `nl {options} file_name` -- number lines of files.
- `tail {options} file_name` -- output the last part of files.
  - Options (most popular):
    - n nums - print the last nums lines, instead of the default 10,
    - f - output appended data as the file grows.
- `head {options} file_name` -- output the first part of files.
  - Options (most popular):
    - n nums - print the first nums lines, instead of the default 10.
- `less file_name` -- display file contents one page at the time.
  - Key commands (most popular):
    - space bar - move down one page,
    - b - move up one page,
    - g - go to the first line,  
    - /search_term - search forward from the current position for the search_term string,
    - ?search_term - search backward from the current position for the search_term string,
    - n - when searching, to to the next occurrence,
    - N - when searching, go to the previous occurrence.
- `od {options} file_name` -- dump files in octal and other formats.
- `base64 {options} file_name` -- base64 encode/decode data and print to standard output.
  - Options (most popular):
    - d - decode data
    - i - when decoding, ignore non-alphabet characters
- `fold {options} file_name` -- wrap each input line to fit in specified width.
  - Options (most popular):
    - b - limit the width of the output by the number of bytes (e.x. b40)
- `gedit` -- text editor for the GNOME Desktop.
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


