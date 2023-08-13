# introduction to the terminal
the shortcut to open a terminal is <strong> ctrl +alt+T </strong>

A shell is a program that takes command from the keyboard and gives it to the computer to run. it also checks if the commands are syntactically correct.

the shell gets started when the user opens or loads a terminal. in essence the shell is xyz@ubuntu20:

The shell is case sensitive

> the most widely use shell is "Bash". other shell applications are Bourne, C shell, korn Shell or Z shell

# WHAT IS A CONSOLE:
a console exists in a non gui distribution while terminal exists in a gui distribution

<code> sudo apt update && sudo apt install terminator </code>

# LINUX COMMAND STRUCTURE

ping -c 1 8.8.8.8
  - ping is the command
  - -c is a command option
  - 1 means we will be pinging only once
  
  > The man page - This command is used to get help. the full meaning is "manual page" and the example is: man [command] e.g man ls
   * g - this is used to move to the beginning of the man page
   * G - used to move to the end
   * / - is used to perform a search
   * q - to quit the man page
  
some commands are built in and as such cannot be seen in the man. just as cd. for such command, use the help followed by the command
<code>type </code> command is used to know whether a command is built-in (shell command) or if it is is available in the man page.

~ a simple trick when it comes to searching for files is to use  <strong> man -k "the command name or a search string" </strong>. eg. <code>man -k "copy files" </strong>. another option is to use the <code> apropos </code> e.g. apropos ifconfig



