 ![Linux](img/linux.jpg)



## Table of contents

- [Linux Commands](#linux-commands)
  - [Managing files & directories](#managing-files--directories)
    - [Basic commands](#basic-commands)
    - [View / Edit file contents](#view--edit-file-contents)
    - [Archive & Compress & extract files](#archive--compress--extract-files)
    - [Special file types (links)](#special-file-types-links)
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

- **`cd`**`examlpe` -- Change directory to *example*.
  - **`cd`**`..` -- move up one directory,
  - **`cd`**`../..` -- move up two directory,
  - **`cd`**`-` -- change to the previous directory,
  - **`cd`**`~` -- change to home directory.
  
- **`pwd`** -- Print the absolute path of current directory.

- **`ls`**`{OPTION}... {FILE}...` -- List directory contents.
  - Options (most popular):
    - *t* - sort the file by modification time,
    - *1* - display one file per line, 
    - *l* - display all information about files/directories,
    - *d* - list directories themselves, not their contents, 
    - *a* - do not ignore hidden files,
    - *i* - print the index number of each file,
    - *S* - sort by file size, largest first
    - *--group-directories-first* - group directories before files.

- **`cp`**`{OPTION}... {SOURCE}... {DIRECTORY}...`  -- Copy *source(s)* to *directory*.
  - Options (most popular):
    - *i* - ask for permission before user overwrite the destination file,
    - *r* - copy the entire directory structure,
    - *p* - preserves the time of the last data modification and the time of the last access, the ownership 
    and the file permission-bits of each source file in the corresponding destination
    file. 

- **`mv`**-- Move (rename) files and directories.
  - **`mv`**`{OPTION}... {SOURCE} {DEST}` - rename *source* to *dest*,
  - **`mv`**`{OPTION}... {SOURCE}... {DIRECTORY}` - move *source(s)* to *directory*.
  - Options (most popular):
    - *i* - prompt before overwriting an existing file,
    - *n* - never overwrite an existing file.

- **`mkdir`**`{OPTION}... {DIRECTORY}...` -- Create the *directory(ies)*, if the do not already exist.

- **`rmdir`**`{OPTION}... {DIRECTORY}...` -- Remove empty *directory(ies)*.

- **`rm`**`{OPTION}... {FILE}...` -- Remove *file* (by default it does not remove directories).
  - Options (most popular):
    - *f* - ignore non-existing files,  
    - *r* - remove directories and their contents,
    - *i* - prompt before every removal,
    - *v* - explain at all time what is being done.

- **`install`**` {OPTION}... {SOURCE}... {DIRECTORY}` -- Copy files (often just compiled) into destination locations.

### View / Edit file contents

- **`touch`**`{OPTION}... {FILE}...`  -- Change file timestamps or create empty file.

- **`cat`**`{OPTION}... {FILE}...` -- Reads data from the file and gives their content as output.
  - **`cat`**`>{FILE}` - create new file with content,
  - **`cat`**`>>{FILE}` - append content to the end of file_name,
  - **`cat`**`{FILE_1} >> {FILE_2}` - append the contents of file1 to the end of file2.
  - Options (most popular):
    - *n* - number all output lines,
    - *b* - number non-empty output lines,
    - *s* - suppress repeated empty output lines.

- **`tac`**`{OPTION}... {FILE}...` -- Write each *file* to standard output, last line first.

- **`nl`**`{OPTION}... {FILE}...` -- Write each *file* to standard output, with line numbers added.

- **`tail`**`{OPTION}... {FILE}...` -- Output the last part of files (by default it's 10 lines).
  - Options (most popular):
    - *n* nums - print the last nums lines, instead of the default 10,
    - *f* - output appended data as the file grows.

- **`head`**`{OPTION}... {FILE}...` -- Output the first part of files (by default it's 10 lines).
  - Options (most popular):
    - *n* nums - print the first nums lines, instead of the default 10.

- **`less`**`{FILE}...` -- Display *file* contents one page at the time.
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

- **`base64`**`{OPTION}... {FILE}` -- Base64 encode or decode *file*, or standard input, to standard
output).
  - Options (most popular):
    - *d* - decode data
    - *i* - when decoding, ignore non-alphabet characters

- **`fold`**`{OPTION}... {FILE}...` -- Wrap each input line to fit in specified width.
  - Options (most popular):
    - *b* - limit the width of the output by the number of bytes (e.x. b40)

- **`gedit`**`{OPTION...} {FILE...}` -- Text editor for the GNOME Desktop.

- **`sort`**`{OPTION}... {FILE}...` -- Sort lines of text files (write sorted concatenation of all 
*file(s)* to standard output).
  - Options (most popular):
    - *r* - sort in reverse order
    - *n* - sort a file numerically
    - *u* - sort and remove duplicates

- **`test`**`{EXPRESSION}` -- Check file types and compare values (exit with the status determined by *expression*).

- **`expand`**`{OPTION}... {FILE}...` -- Convert tabs to spaces.

- **`unexpand`**`{OPTION}... {FILE}...` -- Convert spaces to tabs.

- **`fmt`**`{OPTION}... {FILE}...` --  Simple optimal text formatter (reformat each paragraph in the *file(s)*, writing to standard output).

- **`pr`**`{OPTION}... {FILE}...` -- Convert text files for printing.

- **`split`**`{OPTION}... {FILE[PREFIX]}` -- Split a file into pieces.

- **`csplit`**`{OPTION}... {FILE} {PATTERN}...` -- Split a file into sections determined by context lines.

- **`grep`**`{OPTION}... {PATTERN} {FILE...}` -- Print lines that match patterns.

- **`shuf`**`{OPTION}... {FILE}` --  Generate random permutations.

- **`uniq`**`{OPTION}... {INPUT {OUTPUT}}` -- Report or omit repeated lines (filter adjacent matching lines from *input*, writting to *output*.

- **`comm`**`{OPTION}... {FILE_1} {FILE_2}` -- Compare sorted files *file_1* and *file_2* line by line.

- **`tsort`**`{OPTION} {FILE}` -- Perform topological sort.

- **`cut`**`{OPTION}... {FILE}...` -- Remove sections from each line of files.

- **`paste`**`{OPTION}... {FILE}...` -- Merge lines of files.

- **`join`**`{OPTION}... {FILE_1} {FILE_2)` -- Join lines of two files on a common field.

### File summary

- **`wc`**`{OPTION}... {FILE}...` -- Show information about the file: number of lines, word count, byte and characters count. 

- **`sum`**`{OPTION}... {FILE}...` -- Checksum and count the blocks in a file.

- **`cksum`**`{FILE}...` -- Checksum and count the bytes in a file.

- **`md5sum`**`{OPTION}... {FILE}...` -- Compute and check MD5 message digest.

- **`sha1sum`**`{OPTION}... {FILE}` -- Compute and check SHA1 message digest.

### Archive & Compress & Extract files

Files that have a **.tar.gz** or a **.tar.bz2** extension are compressed archive files. A file with just a **.tar** extension is 
is a single, uncompressed file, that stores many files. The **.gz** or **.bz2** extension suffix indicates that the archive has been compressed, using
either the gzip or bzip2 compression algorithm. 

- **`tar`**`{OPTION}... {ARCHIVE_FILE} {FILE_OR_DIRECTORY_TO_BE_ARCHIVED}` -- Create Archive and extract the Archive files.
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
    $ tar cvzf images_italy_2020.tar.gz /home/user/italy_2020/
    ```
    *Above command will create compressed **image_italy_2020.tar.gz** file for **italy_2020** directory in current 
    working directory.*
    
    ---
    
    - **Create tar.bz2 archive file with `-cvfj` option:**
    ```
    $ tar cvfj images_oslo_2020.tar.bz2 /home/user/oslo_2020/
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
    untar in a different directory, e.x. **~/Desktop/tmp/**. With `-xvf` option we can also extract .tar.gz or .tar.bz2 file.*
    
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
    
### Special file types (links)

A **hard link** is a direct link to the data on disk. This means data can be accessed directly via an original filename or a 
hard link. Both the original file and the hard link are direct links to the data on disk. The use of a hard link allows 
multiple filenames to be associated with the same data on disk.

A **symbolic link** (also sometimes known as a soft link) does not link directly to the data on disk but to another link to the 
data on disk. On most operating systems folders may only be linked using a symbolic link.

- **`ln`**`{OPTION}... {TARGET} {FILE}` -- Make links between files (if the -s option is not specified, it will create 
hard link).
  - Options (most popular):
    - *s -* create symbolic link instead of hard link.
- **`readlink`**`{OPTIONS}... {FILE}...` -- Print resolved symbolic links or canonical file names.
- **`unlink`**`{FILE}` -- Remove the specified file.

### File permission

Every file and directory on Linux system is assigned 3 types of owner, given below:
- **User** - Who is the owner of a file. By default, the person who created a file becomes its
owner.
- **Group** - Can contain multiple users. All users belonging to a group will have the same 
access permissions to the file. Suppose you have a project where a number of people require 
access to a file. Instead of manually assigning permissions to each user, you could add all 
users to a group, and assign group permission to file such that only this group members and
no one else can read or modify the files.
- **Others** - Any other user who has access to a file. This person has neither created the
file, nor he belongs to a user group who could own the file. Practically, it means everybody
else. 

In Linux, every file and directory has it's own three permissions defined for all the 3 owners
discussed above:

- **Read** - This permission allows you to open and read a file.
- **Write** - The write permission gives you the authority to modify the contents of a file. 
The write permission on a directory gives you the authority to add, remove and rename files 
stored in the directory.
- **Execute** - In Linux, you cannot run a program unless the execute permission is
set. If the execute permission is not set, you might still be able to see/modify the program
code(provided read & write permissions are set), but not run it.

On the picture below we can see that the owner of the *random_file.txt* has `rw-` permission, the group
and the others have `r--` permission. The first sign of permission stands for type of the file.

![F_Permission](img/f_permission.png)

The most popular command that enable us to change the file permission (read, write, execute) 
for the owner, group and the world has the syntax as follow:
- **`chmod`**`{PERMISSION} {FILE}...` -- Change file permission.

The table below gives all possible combinations of a file *permission* that each file can have:

| Number        | Symbol          | Permission              |        
| :------------:|:---------------:|:------------------------|
| 0             | ---             | No permission           |
| 1             | --x             | Execute                 |
| 2             | -w-             | Write                   |
| 3             | -wx             | Write + Execute         |
| 4             | r--             | Read                    |
| 5             | r-x             | Read + Execute          |
| 6             | rw-             | Read + Write            |
| 7             | rwx             | Read + Write + Execute  |

There are 2 ways to use **`chmod`** command:

- By specifying permission as a **three-digit octal number** (you change permission for all 3 owners).
![number-mode](img/f-permission-number-mode.png)

- By specifying permission as **symbolic mode** (so that you can modify permission of a specific group).
![symbolic-mode](img/f-permission-symbolic-mode.png)

The table below contains all symbols you will need in order to use symbolic mode:

| Symbol        | Meaning                                                  |       
| :------------:|:--------------------------------------------------------:|
| +             | Add a permission to a file or directory                  |
| -             | Remove the permission                                    |
| =             | Set a permission and overwrite the permission set earlier|
| u             | User/owner                                               |
| g             | Group                                                    |
| o             | Others                                                   |
| a             | All                                                      |


In order to change file ownership or group, the following commands are used:
- **`chown`**`{OPTIONS}... {OWNER{:GROUP}} {FILE}...` -- Change file owner and group.
- **`chgrp`**`{OPTIONS}... {GROUP} {FILE}...` -- Change group ownership.


## File system management

- **`df`**`{OPTION}... {FILE}...` -- Display information related to file systems 
about total space and available space. If no file name is given, it displays the 
space available on all currently mounted file systems.
- **`du`**`{OPTION}... {FILE}...` -- Summarize disk usage of the set of files, 
recursively for directories.
  - Options (most popular):
    - *c* - produce a grand total,
    - *h* - print size in human readable format,
    - *d* - display only a total size for each argument.
- **`stat`**`{OPTION}... {FILE}...` -- Display file or file system status.
- **`truncate`**`{OPTION}... {FILE}...` --  Shrink or extend the size of a file to the 
specified size.

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


