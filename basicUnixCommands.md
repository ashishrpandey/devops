## Command	            Description
* **pwd**		prints working directory (prints to screen, ie displays the full path, or your location on the filesystem)
* **ls**	lists contents of current directory
* **ls –l**	lists contents of current directory with extra details
* **ls /home/user/*.txt**	lists all files in /home/user ending in .txt
* **cd**	change directory to your home directory
* **cd ~**	### change directory to your home directory
* **cd /scratch/user**	change directory to user on scratch
* **cd -**	change directory to the last directory you were in before changing to wherever you are now
* **mkdir mydir**	makes a directory called mydir
* **rmdir mydir**	removes directory called mydir.  mydir must be empty
* **touch myfile**	creates a file called myfile.  updates the timestamp on the file if it already exists, without modifying its contents
* **cp myfile myfile2	copies myfile to myfile2.  if myfile2 exists, this will overwrite it!
* **rm myfile**	removes file called myfile
* **rm –f myfile**	removes myfile without asking you for confirmation. useful if using wildcards to remove files ***
* **cp –r dir newdir**	copies the whole directory dir to newdir.  –r must be specified to copy directory contents recursively
* **rm –rf mydir**	this will delete directory mydir along with all its content without asking you for confirmation! ***
* **nano**	opens a text editor. see ribbon at bottom for help.  ^x means CTRL-x.  this will exit nano
* **nano new.txt**	opens nano editing a file called new.txt
* **cat new.txt**	displays the contents of new.txt
* **more new.txt**	displays the contents of new.txt screen by screen. spacebar to pagedown, q to quit
* **head new.txt**	displays first 10 lines of new.txt
* **tail new.txt**	displays last 10 lines of new.txt
* **tail –f new.txt**	displays the contents of a file as it grows, starting with the last 10 lines. ctrl-c to quit.
* **mv myfile** newlocdir	moves myfile into the destination directory newlocdir
* **mv myfile** newname	renames file to newname.  if a file called newname exists, this will overwrite it!
* **mv dir subdir**	moves the directory called dir to the directory called subdir
* **mv dir newdirname**	renames directory dir to newdirname
* **top**	displays all the processes running on the machine, and shows available resources
* **du –h --max-depth=1**	run this in your home directory to see how much space you are using.  don’t exceed 5GB
* **ssh servername**	goes to a different server.  this could be queso, brie, or provolone
* **grep pattern files**	searches for the pattern in files, and displays lines in those files matching the pattern
* **date**	shows the current date and time
* **anycommand > myfile**	redirects the output of anycommand writing it to a file called myfile
* **date > timestamp**	redirects the output of the date command to a file in the current directory called timestamp
* **anycommand >> myfile**	appends the output of anycommand to a file called myfile
* **date >> timestamp**	appends the current time and date to a file called timestamp.  creates the file if it doesn’t exist
* **command1 | command2**	“pipes” the output of command1 to command2.  the pipe is usually shift-backslash key
* **date | grep Tue**	displays any line in the output of the date command that matches the pattern Tue. (is it Tuesday?)
* **tar -zxf archive.tgz**	this will extract the contents of the archive called archive.tgz.  kind of like unzipping a zipfile. ***
* **tar -zcf dir.tgz dir**	this creates a compressed archive called dir.tgz that contains all the files and directory structure of dir
* **time** anycommand	runs anycommand, timing how long it takes, and displays that time to the screen after completing anycommand
* **man** anycommand	gives you help on anycommand
* **cal -y**	free calendar, courtesy unix
* **CTRL-c**	kills whatever process you’re currently doing
