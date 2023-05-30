
## USER ACCOUNTS AND GROUPS

* To create a new user, run  <code> useradd <code>
    * -d : for user home directory e.g -d /home/userhome_directory
    * -m :  by adding this, the user home directory will be same as the creating user
    * -e : specifies the date the account will expire .e.g useradd gabby -b 2022-11-21
    * -f : the number of days before the account expires e.g. useradd gabby -f 2
    * -s  : sets the default shell type e.g. useradd gabby -s /bin/bash . use nologin or false to prevent the user from logging in
    * -c : sets a comment for the user e.g. useradd  -c "This user is a C++ developer" gabby
    * -g : add the user to a different primary group. e.g useradd -g another_primary_group gabby
    * -G : add the user to secondary groups. e.g useradd -G sec_group1, sec_group2 gabby . note that the groups must exists
    * -a : used to append a user to a group. note that adding a user to a group without adding this flag will remove the user from other groups.

    to get the password policy of the user, run <code> chage -l [user_name] </code>

* to add a passwd to a user run <code> passwd user_name </code>
* to delete a user run <code> userdel -r </code>. the r will remove all directories relating to the user. be careful here
* run <code> id user_name  </code> to view the user group

* usermod is used to change the user. for e.g usermod -c "The user does not know how to code" james

### GROUPS

> The user group is save in /etc/group. IN LINUX, there are 2 type of groups:
1. Primary group: this is the default group of the user. a user can have only one primary group. All files created by that user also belong to the primary group this is denoted by the gid when you run <code> id [username] </code>
2. Secondary groups: A user can belong to multiple secondary groups. when this happends, the user can access any file attached to any secondary group that he belongs to.

run <code> sudo visudo </code> to whitelist group permissions from the file

/etc/passwd, /etc/shadow, /etc/group , /etc/gshadow, /etc/login.defs

* groupadd [groupname] : to create a new group
* groupdel [groupname] : to delete a group
* groupmod -G [groupname] [username] or groupmod -n [new group name] [old group name]

## USER ACCOUNT MONITORING
there are 2 types of user IDs when it comes to monitoring accounts:
1. RUID : Rear user ID: This is the id of the user that was logged in before switching with the su command to another user. run <code> who </code> for this
2. EUID : Effective User ID : This is the ID of the current logged in user or is currently executing commands in the shell. run <code> whoami </code> for this.

The /var/log/wtmp is used by the system to keep a log of the user activities. some of the vital commands when monitoring are:
* uptime :  The uptime utility displays the current time, the length of time the system has been up, the number of users, and the load average of the system over the last 1, 5, and 15 minutes.
* w : The w utility prints a summary of the current activity on the system, including what each user is doing.  The first line displays the current time of day, how long the system has been running, the number of users logged into the system, and the load averages.  The load average numbers give the number of jobs in the run queue averaged over 1, 5 and 15 minutes.
* who : The who utility displays information about currently logged in users.  By default, this includes the login name, tty name, date and time of login and remote hostname if not local.
* last : Last will list the sessions of specified users, ttys, and hosts, in reverse time order.  Each line of output contains the user name, the tty from which the session was conducted, any hostname, the start and stop times for the session, and the duration of the session.  If the session is still continuing or was cut short by a crash or shutdown, last will so indicate.




