- ***Shell***: A command line program that takes keyboard commands and passes to operating system to carry out.
***!*** Shell can be used in virtual console (CLI) or in terminal emulator (when using GUI)

- ***Bash***: A type of shell program.

- ***Program*** is a set of instructions written in programming language and to be understand by computer program need to be converted into machine code (compiled)

---



---

*username@machinename [pwd]* *$,# -* is a Shell prompt

### Metacharacters

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
    - Runs a command in the background (e.g
