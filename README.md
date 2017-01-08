# Cheat
My personal cheatsheet to the Mac OS Terminal (under construction 🚧👷)

![Cheat: Terminal Cheatsheet](https://raw.githubusercontent.com/SebastianBoldt/Cheat/master/terminal.png)

##The Shell
In order to use commands you'll need a program that reads and executes them. That program
is called shell, which runs inside the Terminal. Some commands are builtin and some commands are external programs. You can check that by using the **type** command.

###Wildcards
| Command | Description |
| ----------- | ----------- |
| ls a\* | List all Files that begin with lowercase a |
| ls \*20 | List files that end with 20 |

### Shell variables 
You can define a shell variables and their values by assigning them:
**VAR=3**
Print it out using a leading $
**echo $VAR**

The Shell comes with some default Variables.

| Variables | Description |
| ----------- | ----------- |
| DISPLAY | The name of your display for opening X Windows |
| HOME | Your home directory |
| LOGNAME | Your login name |
| MAIL | Your incoming mailbox |
| OLDPWD | You shells's previous directory, prior to the last cd command |
| PATH | Your shell search path: directories separate by colons |
| PWD | Your shells current directory |
| SHELL | The path to your shell |
| TERM | The type of your terminal |
| USER | Your login name  |

Use **printenv** to print all of them.
If you want to create an environment variable that is available to all programms started from that shell you need to use 
**export VAR=3** or **export VAR** if you previously defined VAR.

###Search path
Programs are scattered all over the filesystem, in directories like /bin and /usr/bin. The variable **PATH** tells the shell where to look.**PATH** is a sequence of directories separated by colons

Modify it using: 
**PATH=$PATH:/your/directory**

if you want to make it permanent you need to put that command into your **.bash_profile**

###Aliases
**alias ll='ls -l'**

**unalias ll**

To make it permanent put it into your .bash_profile

##Filesystem
| Command | Description |
| ----------- | ----------- |
| cd | change to your home directory |
| cd /dir | change to **dir** |
| cd ../dir | change to parents sub directory **dir** |
| cd ./dir | change to current sub directory **dir** |
| pwd | print name of current working directory |
| echo ~ | print path of home directory |

##File Protection

Example: -rw-r--r--

| Postion | Meaning |
| ----------- | ----------- |
| 1 | File type. -(plain file), d(Directory), l(symbolic link), p(named Pipe), c(character device) b(block device) |
| 2-4 | Owner permissions, read, write, and execute permissions for the files's owner |
| 5-7 | Group permissions, read, write, and execute permissions for the files's group |
| 8-10 | World permissions, read, write, and execute permissions for all other users |
