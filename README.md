 ![Linux](img/linux.jpg)



## Table of contents

- [Linux Commands](#linux-commands)
  - [Managing files & directories](#managing-files--directories)
    - [Basic commands](#basic-commands)
    - [View / Edit file contents](#view--edit-file-contents)
    - [Archive & Compress & extract files](#archive--compress--extract-files)
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

- **`cd`**`examlpe` -- change directory to *example*.
  - **`cd`**`..` -- move up one directory,
  - **`cd`**`../..` -- move up two directory,
  - **`cd`**`-` -- change to the previous directory,
  - **`cd`**`~` -- change to home directory.
  
- **`pwd`** -- print the absolute path of current directory.

- **`ls`**`{OPTION}... {FILE}...` -- list directory contents.
  - Options (most popular):
    - *t* - sort the file by modification time,
    - *1* - display one file per line, 
    - *l* - display all information about files/directories,
    - *d* - list directories themselves, not their contents, 
    - *a* - do not ignore hidden files,
    - *i* - print the index number of each file,
    - *S* - sort by file size, largest first
    - *--group-directories-first* - group directories before files.

- **`cp`**`{OPTION}... {SOURCE}... {DIRECTORY}...`  -- copy *source(s)* to *directory*.
  - Options (most popular):
    - *i* - ask for permission before user overwrite the destination file,
    - *r* - copy the entire directory structure,
    - *p* - preserves the time of the last data modification and the time of the last access, the ownership 
    and the file permission-bits of each source file in the corresponding destination
    file. 

- **`mv`**-- move (rename) files and directories
  - **`mv`**`{OPTION}... {SOURCE} {DEST}` - rename *source* to *dest*,
  - **`mv`**`{OPTION}... {SOURCE}... {DIRECTORY}` - move *source(s)* to *directory*.
  - Options (most popular):
    - *i* - prompt before overwriting an existing file,
    - *n* - never overwrite an existing file.

- **`mkdir`**`{OPTION}... {DIRECTORY}...` -- create the *directory(ies)*, if the do not already exist.

- **`rmdir`**`{OPTION}... {DIRECTORY}...` -- remove empty *directory(ies)*.

- **`rm`**`{OPTION}... {FILE}...` -- remove *file* (by default it does not remove directories).
  - Options (most popular):
    - *f* - ignore non-existing files,  
    - *r* - remove directories and their contents,
    - *i* - prompt before every removal,
    - *v* - explain at all time what is being done.

- **`install`**` {OPTION}... {SOURCE}... {DIRECTORY}` -- copy files (often just compiled) into destination locations.

### View / Edit file contents

- **`touch`**`{OPTION}... {FILE}...`  -- change file timestamps or create empty file.

- **`cat`**`{OPTION}... {FILE}...` -- reads data from the file and gives their content as output.
  - **`cat`**`>{FILE}` - create new file with content,
  - **`cat`**`>>{FILE}` - append content to the end of file_name,
  - **`cat`**`{FILE_1} >> {FILE_2}` - append the contents of file1 to the end of file2.
  - Options (most popular):
    - *n* - number all output lines,
    - *b* - number non-empty output lines,
    - *s* - suppress repeated empty output lines.

- **`tac`**`{OPTION}... {FILE}...` -- write each *file* to standard output, last line first.

- **`nl`**`{OPTION}... {FILE}...` -- write each *file* to standard output, with line numbers added.

- **`tail`**`{OPTION}... {FILE}...` -- output the last part of files (by default it's 10 lines).
  - Options (most popular):
    - *n* nums - print the last nums lines, instead of the default 10,
    - *f* - output appended data as the file grows.

- **`head`**`{OPTION}... {FILE}...` -- output the first part of files (by default it's 10 lines).
  - Options (most popular):
    - *n* nums - print the first nums lines, instead of the default 10.

- **`less`**`{FILE}...` -- display *file* contents one page at the time.
  - Key commands (most popular):
    - space bar - move down one page,
    - b - move up one page,
    - g - go to the first line,  
    - /search_term - search forward from the current position for the search_term string,
    - ?search_term - search backward from the current position for the search_term string,
    - n - when searching, to to the next occurrence,
    - N - when searching, go to the previous occurrence.
- **`od`**`{OPTION}... {FILE}...` -- write an unambiguous representation, octal bytes by default, of 
*file* to standard output.

- **`base64`**`{OPTION}... {FILE}` -- base64 encode or decode *file*, or standard input, to standard
output).
  - Options (most popular):
    - *d* - decode data
    - *i* - when decoding, ignore non-alphabet characters

- **`fold`**`{OPTION}... {FILE}...` -- wrap each input line to fit in specified width.
  - Options (most popular):
    - *b* - limit the width of the output by the number of bytes (e.x. b40)

- **`gedit`**`{OPTION...} {FILE...}` -- text editor for the GNOME Desktop.

- **`sort`**`{OPTION}... {FILE}...` -- sort lines of text files (write sorted concatenation of all 
*file(s)* to standard output).
  - Options (most popular):
    - *r* - sort in reverse order
    - *n* - sort a file numerically
    - *u* - sort and remove duplicates

- **`test`**`{EXPRESSION}` -- check file types and compare values (exit with the status determined by *expression*).

- **`expand`**`{OPTION}... {FILE}...` -- convert tabs to spaces.

- **`unexpand`**`{OPTION}... {FILE}...` -- convert spaces to tabs.

- **`fmt`**`{OPTION}... {FILE}...` --  simple optimal text formatter (reformat each paragraph in the *file(s)*, writing to standard output).

- **`pr`**`{OPTION}... {FILE}...` -- convert text files for printing.

- **`split`**`{OPTION}... {FILE[PREFIX]}` -- split a file into pieces.

- **`csplit`**`{OPTION}... {FILE} {PATTERN}...` -- split a file into sections determined by context lines.

- **`grep`**`{OPTION}... {PATTERN} {FILE...}` -- print lines that match patterns.

- **`shuf`**`{OPTION}... {FILE}` --  generate random permutations.

- **`uniq`**`{OPTION}... {INPUT {OUTPUT}}` -- report or omit repeated lines (filter adjacent matching lines from *input*, writting to *output*.

- **`comm`**`{OPTION}... {FILE_1} {FILE_2}` -- compare sorted files *file_1* and *file_2* line by line.

- **`tsort`**`{OPTION} {FILE}` -- perform topological sort.

- **`cut`**`{OPTION}... {FILE}...` -- remove sections from each line of files.

- **`paste`**`{OPTION}... {FILE}...` -- merge lines of files.

- **`join`**`{OPTION}... {FILE_1} {FILE_2)` -- join lines of two files on a common field.

### File summary

- **`wc`**`{OPTION}... {FILE}...` -- show information about the file: number of lines, word count, byte and characters count. 

- **`sum`**`{OPTION}... {FILE}...` -- checksum and count the blocks in a file.

- **`cksum`**`{FILE}...` -- checksum and count the bytes in a file.

- **`md5sum`**`{OPTION}... {FILE}...` -- compute and check MD5 message digest.

- **`sha1sum`**`{OPTION}... {FILE}` -- compute and check SHA1 message digest.

### Archive & Compress & Extract files
Files that have a **.tar.gz** or a **.tar.bz2** extension are compressed archive files. A file with just a **.tar** extension is 
is a single, uncompressed file, that stores many files. The **.gz** or **.bz2** extension suffix indicates that the archive has been compressed, using
either the gzip or bzip2 compression algorithm. 

- **`tar`**`{OPTION}... {ARCHIVE_FILE} {FILE_OR_DIRECTORY_TO_BE_ARCHIVED}` -- create Archive and extract the Archive files.
  - Options (most popular):
    - *c -* create archive,
    - *x -* extract archive,
    - *f -* creates archive with given filename,
    - *t -* displays or lists files in archived file,
    - *u -* archives and adds to an existing archive file,
    - *v -* display verbose information, 
    - *A -* concatenates the archive files,
    - *z -* zip, tells tar command that create tar file using gzip,
    - *j -* filer archive tar file using tbzip,
    - *W -* verify a archive file,
    - *r -* update or add file or directory in already existed .tar file
    
  **Examples**:
    - **Create tar archive file with `-cvf` option:**
    ```
    $ tar -cvf this_is_new_archive.tar ~/Desktop/Python_Examples/
    ```
    *Above command will create a tar archive file called **this_is_new_archive.ta**r for **Python_Examples** directory 
    in current working directory.*
    
    ---
    
    - **Create tar.gz archive file with `-cvzf` option:**
    ```
    $ tar -cvzf images_italy_2020.tar.gz /home/user/italy_2020/
    ```
    *Above command will create compressed **image_italy_2020.tar.gz** file for **italy_2020** directory in current 
    working directory.*
    
    ---
    
    - **Create tar.bz2 archive file with `-cvfj` option:**
    ```
    $ tar -cvfj images_oslo_2020.tar.bz2 /home/user/oslo_2020/
    ```
    *Above command will create compressed **image_oslo_2020.tar.bz2** file for **oslo_2020** directory in current 
    working directory.*
    
    ---
    
    - **Extract or uncompress file with `-xvf` option:**
    ```
    $ tar -xvf this_is_archived_file.tar
    or
    $ tar -xvf this_is_archived_file.tar -C ~/Desktop/tmp/
    ```
    *Above command will untar **this_is_archived_file.tar** file in current working directory. We can use *`-C`* option to
    untar in a different directory, e.x. **~/Desktop/tmp/***
    
    ---
    
    - **List content of an archive file with `-tvf` option:**
    ```
    $ tar -tvf archive_file.tar.bz2
    ```
    
    ---
    
    - **Extract a single file from an archive tar file with `-xvf` option:**
    ```
    $ tar -xvf from_where.tar fiele_name.pdf
    ```
    *Above command will extract **file_name.pdf** from **from_where.tar**. To extract a file from **.tar.gz** use *`-zxvf`* option 
    and from file **.tar.bz2** use *`-jxvf`* option.*
    
    ---
    
    - **Add files and directories to tar archive file with *`-rvf`* option:**
    ```
    $ tar -rvf photos_france.tar paris.jpg
    ```
    *Above command will append **paris.jpg** file to an archive tar file called **photos_france.tar**. The command tar does not
    support appending files to compressed tar.gz or tar.bz2 files.*
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


