# finding files and Directorues
  there are two commmnds for locating files:
 ### mlocate : 
 this is not installed by default on ubuntu so to install it, run apt install mlocate. this is faster than <code>find<code> command. Also noet that the database used by mlocate must be updated periodically using the <code> sudo updatedb</code> command. In other versions of ubuntu or in the mac OS mlocate is replaced by <code> locate </code>
 > the basic usage of the locate command is <code> locate [ file or directory] </code>. running this command will return all paths that have the name of the file or directory been searched for. The locate database is located in /var/lib/mlocate or The locate database (/var/db/locate.database) in MAC OS.
 * -b: will return results where the keyword is only in the paths' basename (i.e where the path ends with the keyword)
 * -w : this is the default behaviuor which returns all paths that has the keyword
 * '\[name]' :  use this in the keyword if you want to return the exact keyword been search for. e.g locate -b '\name' will return the path whose base name is exactly '\name'
 * -e : used to fetch only exisiting files
 * -i : used to make the search case insensitive
 * -r ; this is used to search using regex. for instance locate -r '^shadow\.[0-9]' will serach for path that starts with shadow.0-9.

 ### which 
  This command is used to find the path of executable commands/files. e.g <code> which rm </code> return /usr/bin/rm. use the -a to return all matching paths

 ### find
 The find command is used to find a file based on specified directory. The syntax is <code> find [directory] [options] [filename]. e.g find . -idname file.txt. note that you can use regex special characters in the filename link "*red*".
 * -i : case insensitive
 * -d or -delete : delete the file when found .e.g find . -name file1.txt. -delete
 * -ls : this is run the ls command in files that it finds e.g find . -name file1.txt -ls
 * -maxdepth 2 : 
 * -perm : search based on permission. e.g -perm 755
 * -name : search by filename
 * -type : used to search based on type. the options are -type d, -type f -size 100k -exec cat {} \;, -type f -mtime -7 -ls

 instead of using the -exec, you can also use the -ok which will cause a prompt at each point

 ## Searching for string pattern in text file
 1. grep : This is the most widely used text pattern searching command. The syntax is <code> grep [the text-to_searct] [the location] </code>
    * -i : search using case insensitive
    * -n : print the line number
    * -w : do a word match
    * -v : negation of the search pattern
    * -R : use recursive search in a directory
    * -s : used to suppress permission error
    * -c : do a count of the search result
    * -A 3: display 3 lines before the match
    * -B 4 : display 4 lines after
    * -C 5 : display 5 line before and after the match

2. strings : while grep is used for searching string in text file, the <code> strings </code> is used to search for texts in bianry files. the syntax is same as the grep.


## comparing file
* cmp [a] [b] : use this to compare files
* sha256sum [a] [b] comapres the hash value for the 2 files
* diff [a] [b] is used to only for comparing text files and it does the comparison line by line. -b (ignore blank line), -w (ignore white spacce), -c (more detailed comparison), -i (ingnore case) , -y ( compare by column).

df -h