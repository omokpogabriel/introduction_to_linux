# COMPRESSING FILES

> The tar command is used to archive and compress a file. it is also used to uncompress the file by adding -x flag. the difference between achieve and compress is that archieve reduces the size of the result while archive sort of bundles the files together. the syntax if <code> tar -flags -name-of-result.tar.gz [file-to-compress1] [file-to-compress2] </code>
e.g. <code> tar -czvf old-file.tar.gz /etc/ </code>
* -c -> create archieve
* -z -> compress the archieve
* -v -> verbose
* -f -> operate to a file
* -x -> extracve tar file : e.g. tar -xzvf old-file.tar.gz 
* -r -> append to a previous archieve
* -u -> append files to the archieve if they are newer
* --exclude -> to exclude some files from the archieve e.g. tar --exclude='*.mkv' -czvf backup.tar.gz ./helloworld.txt
* -t -> display the table of content .i.e list the files in an archieve

> you can also use the bzip2 by running tar -cjvf etc.tar.bz2 ./Desktop/hello.txt
<Strong> To extract an achieve to another directory add the -C flag. e.g tar -xjvf etc.tar.bz2 -C ~/my_backup</Strong>

to create an auto backup use <code> tar -cjvf etc.$(date +%F).tar.bz2 /etc


# /ETC/PASSWD AND THE /ETC/SHADOW FILES

## /etc/passwd
the /etc/passwd file show information about each Account user. the format is: root:*:0:0:System Administrator:/var/root:/bin/sh
root : this is the logged in user
* : indicates the user password which is saved in the shadow file
* 0 : the user id
* 0 : the user group
* System Administrator : is the comment
* /var/root : the users home directory
* /bin/sh : default shell. if this is false or empty it means that the user is not allowed to login into the system

## /etc/shadow
 this file stores the actual password of the user in an encrypted format. This is only readable by the root account. each line contains 9 comma seperated fields. checkout "man shadow" for more details


