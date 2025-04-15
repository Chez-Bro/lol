# Table of contents 

 [1. Commands](#1-commands)
 - [chmod](#chmod)
- [less](#less)
- [man](#man)

[2. Terminologies](#2-terminologies)

# 1. Commands 

## Chmod

chomd +x - gives permission for a file to be executable 

you can check it with ls -l command

script.sh

-rw-------. (not executable)

-rwx------. (executable)

Now after given permission we can execute script.sh with ./script.sh

## Less

`*<N>* *<command>* `- N is a number and where is character * means you can use N to this command (see manual).

---

g - first page

G - last page

SPACE - forward the window 

b - backward the window

d - forward the 1/2 the window

u - backward the 1/2 the window

t - Go to the (N-th) next tag.      

T - Go to the (N-th) previous tag.   

{  (  [ - Find close bracket } ) ].        

}  )  ] - Find open bracket { ( [.

---

p - go to a position N percent (range 0-100)

---

/*pattern* - search 

?*pattern* - reverse search

&*pattern* - display only matching lines (if without *pattern* will remove filter)

n - next matching search 

N - previous matching search

Esc + u - undo highlighting

---

:e *[file]* - opens file 

:n - Examine the (N-th) next file from the command line.                  

:p - Examine the (N-th) previous file from the command line.

:x - Examine the first (or N-th) file from the command line.

Ctrl+o n - search forward for hyperlink 

Ctrl+o p - search backward for hyperlink 

Ctrl+o twice - Open the currently selected OSC8 hyperlink.

:d - Delete the current file from the command line list.               

=, :f - Print current file name.

---

!*command* - execute shell command in prompt

v - open editor 

s *[file]* - save input to a file.

## Man

man *[1 item] [item.1] [item(1)]*

man -f *[item]*  shows a short description of found manual pages. ¡Equivalent to whatis command.

man -k *[item]*  searchs all related manual pages to the item. ¡Equivalent to apropos command.

Sections of the manual:

1. Commands
2. Sytem calls
3. Library calls
4. Special files
5. File formats and conventions
6. Games
7. Miscellaneous (mixed)
8. System administration commands
9. Kernel routines

Default order of sections to search:

**1 1p n l 8 3 3p 0 0p 2 3type 5 4 9 6 7**

---

A manual page consists of **sections:**

- NAME
- SYNOPSIS
- CONFIGURATION
- DESCRIPTION
- OPTIONS
- EXIT STATUS
- RETURN VALUE
- ERROR
- ENVIRONMENT
- FILES
- VERSIONS
- STANDARDS
- NOTES
- BUGS
- EXAMPLE
- AUTHORS
- SEE ALSO.

---

### SYNOPSIS (and Flags like *-ab*)

**bold text**

Type exactly as shown.

*italic text*

Replace with appropriate argument.
**[-abc**]

Any or all arguments within [ ] are optional.
**-a l -b**

Options cannot be used together.
**argument …**

Argument is repeatable with any other arguments.
**[expression] …**

Entire expression within [ ] is repeatable with any other [ ].

---

# 2. Terminologies

dmesg: Prints kernel ring buffer, like journalctl 

zram (zswap): A kernel module 

buffer: An open file
