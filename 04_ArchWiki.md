# 1. Shell

**Shell**: A command line program that takes keyboard commands and passes to operating system to carry out.

> Shell can be used in virtual console (CLI) or in terminal emulator (when using GUI)

*username@machinename [pwd]* *$,#* is a Shell prompt

## 1.1 Bash 
**Bash**: Type of shell program

## 1.2 Metacharacters 

**Metacharacters**: Special characters with specific meanings to the shell and are used to perform various actions:

1. **`$`**:
    - Used for variable expansion (e.g., `$HOME` to access the home directory).
    - Used for command substitution (e.g., `$(command)`).
2. **`#`**:
    - Used for comments in scripts. Anything following `#` on a line is ignored by the shell.
3. **`~`**:
    - Represents the home directory of the current user.
4. **`/`**:
    - Directory separator (used in paths).
5. **`\\`**:
    - Escape character, used to escape special characters (e.g., `\\$`).
6. **`|`** (Pipe):
    - Sends the output of one command as the input to another command.
7. **`>`**:
    - Redirects the output of a command to a file, overwriting it (e.g., `echo "Hello" > file.txt`).
8. **`>>`**:
    - Redirects the output of a command to a file, appending to the file (e.g., `echo "Hello" >> file.txt`).
9. **`<`**:
    - Redirects input from a file to a command (e.g., `command < file.txt`).
10. **`&`**:
    - Runs a command in the background (e.g., `command &`).
    - Can be used to combine commands, e.g., `command1 & command2`.
11. **`&&`**:
    - Executes the second command only if the first command succeeds (e.g., `command1 && command2`).
12. **`||`**:
    - Executes the second command only if the first command fails (e.g., `command1 || command2`).
13. **`;`**:
    - Allows you to separate multiple commands on a single line (e.g., `command1; command2`).
14. **`()`**:
    - Used for command grouping and subshells. Executes commands inside the parentheses in a new shell (e.g., `(command1; command2)`).
15. **`{}`**:
    - Used for grouping commands in the current shell (e.g., `{ command1; command2; }`).
16. **`` (backticks)**:
    - Older method of command substitution, executes a command and substitutes its output (e.g., `echo `date`` ).
17. **`!`**:
    - Negates a condition in some commands or test expressions (e.g., `! command`).
    - Used to refer to previous commands in Bash history (e.g., `!3` to run the 3rd command in history).
18. **`()` (Parentheses)**:
    - Used for process grouping or running commands in the background.
    - Example: `(command1; command2)` runs in a subshell.
19. **`$(( ))`**:
    - Used for arithmetic evaluation (e.g., `result=$((3 + 5))`).

# 2. Navigation

`pwd`: Prints name of current/working directory.

`cd`: Changes working directory.

`ls`: Lists directory contents.

## 2.1 Filesystem Hierarchy Standard

**Filesystem Hierarchy Standard (FHS)**: An organization of files in Linux.

>Note:
>Linux has 1 filesystem tree for all drives and storage devices. `/`

![1000026702.jpg](Navigation%2016e244188b778014a266ffcdf285371a/1000026702.jpg)

## 2.2 Absolute pathname    

**Absolute pathname** starts from the root /.

`cd /FULL/PATH/NAME`
## 2.3 Relative Pathname

**Reative Pathname** starts from your current directory.

`cd ..`
`cd SUBDIRECTORY` 

> Tip:
> It can be used for multiple directories change.
> `cd ../../..` 

---

## 2.4 cd command shortcuts

`cd -`: Changes the working directory to the previous working directory.

`cd ~`: Changes the working directory to the home directory of *user_name*. 

---
## ?  Mount

`mount`: Attachs a strorage device to drives at specific point on file system tree, it allows the device to interact with the operating system.

## ? Pacman 
pacman installed packages directory: */var/cache/pacman/pkg*/

> pacman -Sc clean old, unused packages’ cache
> 
# 3. Exploring the system

`ls PATH`: Lists contents of the directory.

`ls -R`: Shows subdirectories.

`ls -a`: Shows all files (hidden files).

`ls -l`: Lists files in long format.

`less`: Displays the contents of a file.

`cat`: Prints the contents of a file.

`reset`: Resets the terminal (if you messed up).

## 3.1 ls -l breakdown

```
$ ls -l

drwxrwxrwx 3 me group 4096 2017-10-26 17:20 file_name
```

---

> More info:
>  [ls(1)](https://man.archlinux.org/man/ls.1p.en) at **STDOUT** section

Default output of `ls -l` command in the following orders:
1. file mode
2. number of links
3. owner name
4. group name
5. size or device name
6. date and time
7. pathname 

## 3.2 Breakdown of the file mode (drwxrwxrwx):

**File type**: The first character can be:

`d`: directory

`-`: regular file

`l`: symbolic link

`c`: character device

`b`: block device

`s`: socket

`p`: named pipe (FIFO)

---

`rwx`: **r**ead, **w**rite, and e**x**ecute permission 

It repeats **3** times in the following orders:

1. owner can read, write and execute.
2. group of the owner can r, w, x.
3. all users can r, w, x.


## 3.3 Breakdown of the links

`ls -l` (second column) tells you how many **hard links** point to that inode.

---

`ls -i`: Lists inodes.

`find -inum INODE`: Finds all files related to the `INODE`.

> Note:
> -  Files usually have only 1 hard link (just their own name).
> - Directories usually start with 2:
> 	1. One for the directory itself.
> 	2. One from its parent (..).

[More info](../Linux%20system%201a6244188b778078992df9abce9254d1/File%20system%20structure%201a6244188b7780259445ed5e94ae9f23.md)

## ? Find and search

`find / -name NAME`

`pacman -Ss *name` -* search for all pkgs related to name 

`pacman -Si name` - info about any pkg even if not installed 

`ls -d [pattern]*[pattern]` - will list dir matched pattern but not before or after * (and only directories -d)

`ls --hide **.**` - hide all files with pattern `.`

# 4. Editing

`touch`: Creates files.

`mkdir`: Creates directories.

`mkdir -p DIRECTORY/SUBDIRECTORY`: Creates a directory and subdirectories.

`rm`: Removes files and directories.

## 4.1 Copy, paste, move, and rename 

`cp TARGET… DESTINATION`: Copies files and directories. 

`mv TARGET… DESTINATION`: Moves or renames files and directories.

`echo TEXT|COMMAND >> FILE`: Moves the `TEXT` or the output of the `COMMAND` to the `FILE` (if only one `>` it also overwrites)

---

**Double click**: Copies a text.

**Middle click**: Pastes a text.

CTRL + K 

CTRL + Y
## 4.2 Hard link

`ln TARGET_FILE LINK_NAME`

**Hard link**: A directory entry with different file name, but with same inode, and both original file and hard links access the same data. When we create a hard link, we create an additional directory entry for a file. 

Hard links have two important limitations:

1. A hard link cannot reference a file outside its own file system. This means a link cannot reference a file that is not on the same disk partition as the link itself.
2. `TARGET` may not be directory to avoid loop

## 4.3 Soft link

`ln -s TARGET LINK_NAME`

**Symbolic link**: A special type of file whose contents are a string that is the pathname of another file, the file to which the link refers. 

>The contents of a symbolic link can be read using [readlink(2)](https://man.archlinux.org/man/readlink.2.en)

[More info](../Linux%20system%201a6244188b778078992df9abce9254d1/File%20system%20structure%201a6244188b7780259445ed5e94ae9f23.md)

---

## 4.4 Wildcards (Globbing)

`*`: Matches any sequence of characters (including none)

`?`: Matches any single character

`[characters]`: Matches any character in the specified set 

`[!characters] or [^characters]`: Matches any character NOT in the specified set

`[:class:]`: Matches any character in the specified character class.

---

### 4.4.1 Commonly Used Character Classes

`[:alnum:]`: Matches any alphanumeric character (**A-Z, a-z, 0-9**

`[:alpha:]`: Matches any alphabetic character (**A-Z, a-z**) 

`[:digit:]`: Matches any numeral (**0-9**)

`[:lower:]`: Matches any lowercase letter (**a-z**)

`[:upper:]`: Matches any uppercase letter (**A-Z**)





