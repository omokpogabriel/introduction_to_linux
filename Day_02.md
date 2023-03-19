
## Bash shortcuts
* use the <b> tab key </b> for auto complete.
* <code> ctrl + L </code> - this clears the screen <i> this is the same thing as typeing <code> clear </code>
* <code> ctrl + D </code>  - closes the bash shell this is the same thing as typing <code> exit </code>
* <code> ctrl + A </code>  - moves the console to the first line
* <code> ctrl + E </code>  - moves the console to the end of the line
* <code> ctrl + U </code>  - deletes everything before the console 
* <code> ctrl + C </code>  - used to end a running process
* <code> ctrl + R </code>  - used to search for a command in history
* <code> ctrl + Z </code>  - used to suspend a running process. note that his does not kill the process like ctrl+c but only stops it. to resume the process type <code> bg %1 </code>
* <code> ip address show </code> - show the ip address of the system
* <code> !! </code> - runs the previous command  . add <code> :p </code> to view the code before running it.
* <code> !<u>SIZE</u> </code> - runs the command that was run the last number 
* <code>history </code> - this command is used to get the history of all the commands run in the terminal
* <code>history -d <u>HISTORY_LINE_NUMBER </u> </code> - used to remove a command from history
* <code>history -c</code> -used to clear the entire history
* <code>sudo passwd [username]</code> - used to change password
  
# BASH HISTORY
> Bash keeps a log of all the commands that has been run in the user home directory. this file name is call <strong> .bash_history </strong>.
  To get the history of commands run on the terminal, type <code> cat .bash_history </code>. to get the size of this file, type <code> eco $HISTFILESIZE </code>
  
## RUNNING COMMANDS WITHOUT LEAVING A TRACE
  > To run commands without adding them to the history add a <strong> whitespace </strong> before the actual command you want to run. this will not add it to the history. note that this only works in ubuntu. To make it run in all distros, do this follow:
  * check is the history is set to ignore the whitespace by typing <code> echo  $HISTCONTROL </code>. if this return <i> ignoreboth </i>, then it will be ignore but if it returns <i> ignoredups </i>, it will not be ignored. to correct this, type <code> HISTCONTROL=ignorespace </code>. this should fix it
  * HISTOMEFORMAT="%d/%m/%y %T"
  *echo HISTTIMEFORMAT="%d/%m/%y %T" >> .bashrc  --  used to persist a settings to the bash so that is is not overwritten when the use restarts the system
  
# ROOTS AND PRIVILEDGES
  There are 2 categories of users :  non priviledged users and root users.
  > sudo su - this is used to switch to the root user. To activate the root user account type <code> sudo su - </code>  then run <code> pwd </code> to view the current working directory. To leave the root user account when using sudo su, type exit. use the exit <br/>
  when you run the sudo command, it caches it for 5 minutes. this mewans that it will not ask for password for the if you run the sudo comand within the next 5 minutes. To update this cache type <code> sudo -v </code>. To invalidate the cache thereby making terminal ask for a password next time you run run, type <code> sudo -k </code>.
  
  
  
