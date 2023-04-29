# UNDERSTANDING PIPES
 There are 3 types of stream in Linux, STDIN, STDOUT AND STDERROR
 > the pipe <code> | </code> is used to make an output become input for another command. It is standard practice to add a space between before and after the pipe. for instance 
 * <code> ls -lSH -n 20 /etc/ | head </code>. The command above gets all the sorted files in the etc directory and using the pipe, sends it to the head command with then gets only the first 10 files. Pipe is a very enssential command. 
 * another example is using the cat and grep. For instance <code> cat /var/log/auth.log -n | grep -a "authentication failed" </code>. This code will return lines containing the text authentication failed.
 * <code> tail ./Desktop/file.txt | wc -l </code> the wc ( stands for word count )-l shows the count of lines that was gotten.

 > wc /etc/passwd will tell you the count of words in the passwd file ( -c is character count, -w is word count -l is line count)

 ## PIPE AND REDIRECTION COMMAND
 > when you want to send the output of a command to a file use <code> > </code>. However, note that this will overrite the content of the file if it exist. to prevent this use <code> >> </code> which will append to the file instead

 > since everything is a file, the terminal is also a file. therefore the output from one terminal can be redirected to a other terminal. run the <code> tty </code> and you will is the file with represents the current terminal window. with this and in combination with the >, you can send data from one terminal to the other. eg. assuming my current terminal is /dev/ttys00p, I can open another terminal and do  <code> echo "hello here" > /dev/ttys00p </code>.

 <Strong> if  you want your error output to be redirected to a file instead of the std add a 2> or 2>> after the command e.g 
        <code> lsa -l /Desktop 2> error.txt </code> Note that there is not space bewteen the 2 and the >
 </Strong>

 > you can redirect the standard error (2>) to the standard output by doing 2>&1. e.g <code> tail -n 2 ./Desktop/file1.txt /etc/shadow  output.txt 2>&1 </code>. this will redirect the error (from /etc/shadow) to output.txt (which is rep by &1).

 > the <code> tee -a [file1] [file2] [file3.....] </code> is used to both write the output to a file and also display the result in the terminal. 