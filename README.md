# Cheat
A cheatsheet to the Mac OS Terminal (under construction 🚧👷)

![Cheat: Terminal Cheatsheet](https://raw.githubusercontent.com/SebastianBoldt/Cheat/master/terminal.png)

##The Shell
In order to use commands you'll need a program that reads and executes them. That program
is called shell, which runs inside the Terminal. Some commands are builtin and some commands are external programs. You can check that by using the **type** command.

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
