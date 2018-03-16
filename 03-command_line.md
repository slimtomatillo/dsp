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

> > `pwd` = show current working directory path  
> > `mkdir` = `mkdir` + `newdirectory` will create a directory  
> > `rm -r` = `rm -r` + `directory` will delete a directory and all of its contents  
> > `rmdr` = `rmdr` + `directory` will delete an empty directory  
> > `touch` = `touch` + `file` will create a file  
> > `rm` = `rm` + `file` will delete a file  
> > `mv` = rename a specified file or directory (or move file)  
> > `ls -a` = list hidden files  
> > `cp` = `cp` + `file` + `directory` copy specified file to specified directory  
> > `echo` = outputs the string of the argument being passed  
> > `ls` = list files in the current working directory  
> > `cat` = displays contents of a file  
> > `cd` = `cd` + `directory` or `path` change directory to specified directory or path  
> > `cd ..` = move up one directory  
> > `history` = displays listing of the last commands run  
> > `wc` = `wc` + `filename` outputs the number of lines, words, and characters in specified file  
> > `grep` = searches for a text pattern and outputs it  
> > `sed` = searches for a text pattern, modifies it, and outputs it  

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

> > `ls` = list files in the current working directory  
> > `ls -a` = list all files including those starting with a dot .  
> > `ls -l` = list files and use a long listing format (which displays permissions, links, owner, group, size, time, and name)  
> > `ls -lh` = list files and use a long listing format with sizes printed in human readable format (e.g., 4K 34M 7G)  
> > `ls -lah` = list all files including hidden . files in long listing format with sizes printed in human readable format  
> > `ls -t` = list files and sort by time, defaults to modification time  
> > `ls -Glp` = list files and inhibit display of group information and use a long listing format and put / after directory names  

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > `ls -m` = list file names as a comma-separated list  
> > `ls -R` = list files and display all subdirectories as well  
> > `ls -i` = list files and display the inode for each file  
> > `ls -1` = list each file on a line  
> > `ls -c` = list files by file timestamp  

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > `xargs` executes commands on multiple arguments or files  

> > *Examples:*  

> > `$ ls | xargs -n 1 chgrp newgroup`  
> > This changes the group of all the files in the current directory to newgroup  

> > `$ ls | xargs rm`  
> > This removes all the files in the current directory  
