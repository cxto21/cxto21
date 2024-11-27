---
title: Intro to shell
date: 2024-11-21 10H:13:00 -0300
categories: [Linux, Shell]
tags: [linux, shell, bash, linux-commands, shell-scripting]
author: 0
description:
image:
  path: https://preview.redd.it/dzml1asbvdz31.png?width=1080&crop=smart&auto=webp&s=7ac7d2bb99dae088cde3ce8aa4b9c8737898524f
  alt: Picture
---

# Command Console and Scripting in Bash

Pipes and Redirections ('|' & '>').
* *Pipes:* The Pipes, '|', allow us to redirect the output of one process to the input of another.
* *Redirections:* The redirections, '>', send the output of a process to the input of a specific file. For example, write a new file after reading another: "$> cat 'existentFile' > 'newFile'".
* *Redirect standard error:* "$> cat 'nonExistentFile' 2> /dev/null", el 2> catch standard error and forward to "blackhole" /dev/null.     

Processes that interact with "the external" do so from file descriptors, except in the case of daemons. In Linux, file descriptors are integers that can range from 0 to 1023, structures that specify some data input or output channel.

*Stdin, Stdout, and Stderr*
* *Standard input:* Stdin: 0, 0<
* *Standard output:* Stdout: 1, 1>
* *Standard Error:* Stderr: 2, 2> 

**Commands in a shell for basic file browsing:**
  * *$> pwd* It shows us in which file address we are located (PATH).
  * *$> ls* We see the files in our current PATH
  * *$> ls -la* We see the hidden files (those that are named starting with "." and we also see information about groups, users and permissions)   
  * *$> tree* We see the files in our PATH in a tree format.
  * *$> tree -r* We see PATH files and recursively their subdirectories.
  * *$> cd 'argument'* We navigate to an absolute address, or relative to our PATH. With something like "$> cd ~" we mean the home folder of the user running the interpreter, something like "$> cd /" will take us to the root of the file system. To go back directories we use dots, we go back one level with "$> cd ..", two levels with "$> cd ..".    
  * *$> find (arguments)* for file search. We can use Pattern Matching, start from certain directories, and from other search criteria. Example: "$> find -not -path '~/NotHere' / -iname '.deb'", we look for .deb files in the name omitting the search for ~/NotHere. 
  * *$> cat 'filePath'* The cat command allows us to read a plain text file. 
  * *$> cat 'filePath' | less* Less is a plain text document viewer which, used in this way, will better display the file in FILEPATH.  
  * *$> cat 'filePath' | more* more is an evolution of less.
**Basic commands for creating files in bash.**
  * *$> touch 'new_nameFile'* Create file
  * *$> mkdir 'new_nameFolder'* Create folder
  * *$> touch 'new_nameFile new1_nameFile new2..'* Create multiple files 
  * *$> mkdir 'new_nameFolder new2_nameFolder ..'* Create multiple folders

**Copy and move files in bash**
  * *$> cp 'pathFile' 'new_pathFile'*  
  * *$> mv 'pathFile' 'destiny_path'*

**Modify filename in bash**
  * *$> mv './nameFile' './new_nameFile'* way to rename a file

**Simple Basic Bash Script Creation:**
  *procedure to create a simple Script and give it execution permission:*
  1. *$> touch basicScript.sh*: Create a file called with the extension sh.
  2. *$> nano basicScript.sh*: Open the nano editor.
     * Write "#!/bin/bash" en la primer linea.
     * Write 'greet="Hi, i'm the very basic bash script"' in the second line.
     * Write "print $greet" in some next line.
     * Save the changes in the file with the key combination (Ctrl + O).
     * Exit nano with Ctrl + X.
  3. Assign execute permissions to the file with "$> chmod u+x basicScript.sh".   
  4. Execute the script with "./basicScript.sh".  
