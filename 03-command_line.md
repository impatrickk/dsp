# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > pwd = show current working directory path, mkdir = creating a directory, rm = deleting a directory, rm -r = delete directory and child directories, touch (filename) = creating a file using `touch` command, rm = deleting a file, mv (filename) (new filename) = renaming a file, ls -a = listing hidden files, cp (file) (new directory) = copying a file from one directory to another, cat (file1) > (file2) = overwrites content in file2 with contents in file1, sort (file) = sorts contents in file alphabetically, uniq (file) = filters out adjacent duplicates, sort (file) | uniq = sorts and filters out duplicates

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

> > "ls" lists the files and directories inside the current directory. "ls -a" lists all files and directories including hidden files/directories. "ls -l" lists the long name of the files/directories. "ls -lh" is the long name option with the sizes in human readable format. "ls -lah" lists all files including hidden files and directories with long name and with sizes in human readable format. "ls -t" lists files by order of last modified. "ls -Glp" lists files and directories in long name with directories identified with a "/" at the end of the name.

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > "-r" will reverse order, "-u" displays files by the file access time, "-R" will show subdirectories as well, "-d" only shows directories, and "-q" displays all nonprinting characters as "?".

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > "xargs" is used to run a command for every item or input in a list
> > ls | xargs rm = removes every file in current directory

 

