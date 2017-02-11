# Terminal-Cheatsheet
My personal cheatsheet for the Mac OS Terminal 

![Cheat: Terminal Cheatsheet](https://raw.githubusercontent.com/SebastianBoldt/Cheat/master/terminal.png)

##The Shell
In order to use commands you'll need a program that reads and executes them. That program
is called shell, which runs inside the Terminal. Some commands are builtin and some commands are external programs. You can check that by using the **type** command.

| Command | Output |
| ----------- | ----------- |
| type ls | ls is an alias for ls -G |
| type pod | pod is Users/username/.rvm/gems/ruby-2.0.0-p247/bin/pod |

###Wildcards
| Command | Description |
| ----------- | ----------- |
| ls a\* | List all Files that begin with lowercase a |
| ls \*20 | List files that end with 20 |

### Shell variables 
You can define a shell variables and their values by assigning them:
``` 
VAR=3 
```
Print it out using a leading $

``` 
echo $VAR
```

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
``` 
export VAR=3 
``` 

or 

``` 
export VAR
``` 

if you previously defined VAR.

###Search path
Programs are scattered all over the filesystem, in directories like /bin and /usr/bin. The variable **PATH** tells the shell where to look.**PATH** is a sequence of directories separated by colons

Modify it using: 
**PATH=$PATH:/your/directory**

if you want to make it permanent you need to put that command into your **.bash_profile** or **.zshrc**

###Aliases
``` 
alias ll='ls -l'
```

```
unalias ll
```

To make it permanent put it into your **.bash_profile** or **.zshrc**

###Input & Output redirection 

The shell can redirect standard in, standard out and standard error to and from files.
Any command that reads from standard input can read from a file instead with the shells **<**, **>** and **2>** operator

| Command | Description |
| ----------- | ----------- |
| command < infile | command should read from file |
| command > outfile | command should write to a file |
| command >> outfile | command should append its output to file |
| command 2> errorfile | write standard error to file & stream |
| command > outfile 2> errorFile | write to outfile and things the command writes to stderror will be redirected to errorFile |

###Pipes 
Redirection of standard input of one command can be redirected to another command using the **|** operator.

| Command | Description |
| ----------- | ----------- |
| ls \| wc -l | redirect ls output to word count command |
| ls -1 \| cut -d. -f2 \| sort | Show all file types |

###Combining Commands 
| Command | Description |
| ----------- | ----------- |
| command1 ; command2 | If anyone fails, the sequence continues |
| command1 && command2 | The sequence will stop if any command fails |
| command1 \|\| command2 | The sequence will stop if one command succeeded |

###Quoting & Escaping 
If you want a word contain whitspaced you need to surround it with single or double quotes to make the shell treat it as a unit.
Double quotes will result in evaluating the actual content and replacing shell variables with there actual content.

| Command | Description |
| ----------- | ----------- |
| wc 'Value of PATH: $PATH' | Will print "Value of PATH: $PATH" |
| wc "Value of PATH: $PATH" | Will print "Value of PATH: /users/sebastian/.." |

If a character has a special meaning to the shell but you want it used literally, precede the character with a backslash \

| Command | Description |
| ----------- | ----------- |
| echo a\\* | Will print **a***, so * will not be interpreted as the wildcard symbol |

###Command History 
The shell allows you to recall previous commands. All commands you are entered are stored inside the command history. Here are some handy command you can use for it 

| Command | Description |
| ----------- | ----------- |
| history | print your history |
| history N | print most recent n commands |
| history -c| clear your history |
| !! | re run previous command |
| !N | rerun command N in history |
| !-N | rerun command you typed n times ago |
| !$| last parameter from previous command |
| !* | all parameters from last command |
| up arrow | go to previous command |
| down arrow | go to next command |

###Jobs 

All shells have job control: the ability to run programs in the background (multitasking) und foreground (running as the active process at your shell). Jobs are higher level than processes.

| Command | Description |
| ----------- | ----------- |
| jobs | List your Jobs |
| emacs myfile & | put emacs to the background |
| ^Z | suspend the current forground job |
| bg [%jobnumber] | send suspended job to the background |
| fg [%jobnumber] | bring it into the foreground |
| suspend | make supsended job run in the background |

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

Example:
``` 
-rw-r--r--
```

| Postion | Meaning |
| ----------- | ----------- |
| 1 | File type. -(plain file), d(Directory), l(symbolic link), p(named Pipe), c(character device) b(block device) |
| 2-4 | Owner permissions, read, write, and execute permissions for the files's owner |
| 5-7 | Group permissions, read, write, and execute permissions for the files's group |
| 8-10 | World permissions, read, write, and execute permissions for all other users |

##Commands

....
