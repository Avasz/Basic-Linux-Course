#Chapter 5 - Introduction to Command Line & Commands

As stated in some of the previous chapters, Linux has CLI mode & GUI mode.  We can also access Command Line in GUI mode by starting a terminal emulator. We have different emulators available for command line in Linux, some are Destop Environment specific and some can be installed independently in any Desktop Environments. Example of some terminal emulators are: 

* gnome-terminal, 
* xfce4-terminal,
* konsole, 
* yakuake, 
* guake etc. 

Command line is used by Linux users for various tasks such as automating processes, troubleshooting tasks in text environment etc.Tasks that are unable to be done using Graphical Interface can be accomplished using command line. Some people even go to the extreme mode by using chat clients, text editors, browsers etc. in command line mode. The command line mode has various advantages, some of them are as follows: 
* No GUI overhead
* Virtually every task can be accomplished using the command line
* Tasks and series of prochedures can be scripted
* Remote login to machines anywhere in the internet
* Initiate graphical apps directly from command line
* Debug applications etc.

A terminal emulator emulates a stand alone terminal within a window in the desktop. This gives us the feeling that we are logging into the machine with a pure text terminal environment.Most terminal emulators nowadays support multiple tabs and features like mouse mode etc. 

Next: Start a terminal window in your Operating System.

###5.1 The Command Line
After starting the terminal you will be greeted by a prompt. eg:  
```shell
bishnu@debian:~/Documents$ _ 
root@debian:/usr/share# _
```


For explaining the prompt we will separate each section of the prompt into different parts.  
1. bishnu: This is the name of the current user you are logged in as. In the second line, it is logged in as **root**.  
2. debian: This is the hostname of the computer you had set during the installations. This can be changed if required. It means, other computers in your network will know your machine with this name.  
3. /Documents or /usr/share: This is the path of your current working directory. You can verify it with the command **pwd**.  
4. $ or #: This ends the prompt. **'$'** means the user is logged in as normal user. And, **'#'** means the user is logged in as the root user.  
5. The space after this is the place for us to enter commands.  

If you want to operate only in Command Line and turn of the graphical desktop environment, then you can issue either of these commands:  
1. sudo systemctl stop gdm (For GNOME)  
2. sudo systemctl stop lightdm  
3. sudo killall -9 Xorg  
4. etc. etc.




####5.1.1 The Commands
Generally, each command entered in command line has three basic elements: 
* Commands
* Options
* Arguements

**Commands** are the name of the programs you are executing which takes one or more **Options**. Options can switch among various tasks that a command can do. **Options** generally start with a single hypher or two hyphens, i.e. '-' or '--'. And **Arguements** represents what the commands operates on. This is general structure of commands, but there are lots of commands that do not have any  options or arguements. 

###5.2 Basic commands

Let us start by knowing who you are. Run  `whoami` in the prompt to know who you are right now.   
 
####5.2.1. Listing Files and Folders - ls
ls command is used for listing the files and directories. Just typing the **ls** command in your prompt will display the files and directories in your current folder. You can type full path of the folder you want to view.
eg:
```shell
user@debian:~$ ls
Documents	Downloads	Music	Public
```

Some useful options of **ls** command:    
* ls -a    
	This displays all the files and directories, even the hidden ones.
eg:
```shell
user@debian:~$ ls -a
. .. .config .fonts Documents Downloads Music Public
```

* ls -l  
	This displays long list
```shell
user@debian:~$ ls -l
total 16
drwxr-xr-x 2 avasz avasz 4096 Mar 18 11:11 Documents
drwxr-xr-x 3 avasz avasz 4096 Mar 18 11:11 Downloads
drwxr-xr-x 2 avasz avasz 4096 Mar 18 11:11 Music
drwxr-xr-x 3 avasz avasz 4096 Mar 18 11:11 Public
```

* Do it yourself: combine the options l & a in same command and find the difference.

####5.2.2. Making Directories - mkdir
**mkdir** command is used to make directories. 
Syntax:  
```shell
mkdir [OPTIONS]... DIRECTORY...
```

**Example:**

```shell
user@debian:~$ mkdir New_Directory
```
After that you can test if the new directory has been created or not by using the **ls** command we learnt earlier.  

One important option that can be used with **mkdir** is the **-p** option. Generally, if you want to create subdirectories in a directory that doesn't exist then **mkdir** will return an error. But if you use **-p** option, then it will create the parent directories as necessary. Example:  
```shell
user@debian:~$ ls
. .. Documents Downloads Music Public

user@debian:~$ mkdir Videos/Songs/English
mkdir: cannot create directory ‘Videos/Songs/English’: No such file or directory

user@debian:~$ mkdir -p Videos/Songs/English

user@debian:~$ 

user@debian:~$ ls
. .. Documents Downloads Music Public Videos

user@debian:~$ ls Videos
Songs

user@debian:~$ ls Videos/Songs
English  
```

####5.2.3 Changing direcotries - cd
The **cd** command can change the direcotry. By default if you do not supply any arguements and just enter **cd**, it will take you to the home directory of the current user.
You can use the **absolute path** or the **relative path** while using **cd** command. Some examples of using the **cd** commands are shown below.

* cd ..  
	This command will take you to the parent directory of the current directory. eg:
```shell
user@debian:~/Videos/Songs$ pwd
/home/user/Videos/Songs

user@debian:~/Videos/Songs$ cd ..
user@debian:~/Videos$ pwd
/home/user/Videos
```

* cd /
This command will take you to the root directory of the file system.

* cd /absolute/path/to/directory
This command will take you to the directory you have specified with full path.
eg:
```shell
user@debian:~$ cd /usr/share/bin/
user@debian:/usr/share/bin$ pwd
/usr/share/bin
```
* cd relative/path/to/directory
This command will take you the the directories with relative path from the current directory. Perform the following task as normal user.  

> 1.  `cd` 
> 2. `mkdir -p new_folder/sub_folder/last_folder`
> 3. `cd new_folder/sub_folder/last_folder` 
> 4. Check your present directory with `pwd`
> 5. If you did everything correctly then you should be in the `last_folder`
> 6. Now, suppose you need to get to the `new_folder` from your current directory. You have two options, either give the full path as `/home/you_user_name/new_folder`, or you can use relative path as `../.../`
> 7. Finally, create another folder inside the `new_folder` named `sub_folder2` and inside that another folder called `tired_of_creating_folders`. `cd` to the `tired_of_creating_folders`, and from here get to the `last_folder` using relative path.

* cd ~
This command will always take you to the home directory of the user you are currently logged in as no matter where you are.

####5.2.4 Checking present working directory - pwd
The `pwd` command will show you your present working directory. Try it in your prompt.

####5.2.5 Creating an empty file - touch
The `touch` command creates a file to the path you specified. In case you did not specify any path, it will create in your **present working directory**.

Syntax:  
`touch filename` or `touch /path/to/the/file/filename`  

Example:
```bash
user@debian:~$ touch file1
user@debian:~$ touch new_folder/file2
```

**You can check if the files have been created or not using the `ls` command if you wish**

####5.2.6 Copying and Moving files - cp & mv
We have learnt about relative and absolute paths in the previous section so we will be using them where possible. Also, we will be working on the two files we created in the previous secions, `file1` and `file2`.    

#####5.2.6.1 cp
The `cp` command is used to copy a file or a folder from one place to another. Syntax:
`cp Source Destination`  
Example:
```bash
user@debian:~$ cp file1 new_folder/
user@debian:~$ ls new_folder/
file1 file2 sub_folder
```

You can also copy the file inside the same folder, for that you do not need to mention the full path.

**Try it yourself:**  
Copy the file named `file2` to the `last_folder` staying in your home directory.

Now, we will check copying the folders.  
> 1. Change your `pwd` to your home directory.
> 2. Create a new directory named copy_folder.
> 3. Try to copy the `new_folder` to `copy_folder` in similar way.
> 4. What does it say?
> 5. It is because the directory is not empty, you need to use recursive option to copy the directories from one place to another. Try it with the **-r** flag. i.e. `cp -r 'new_folder` `copy_folder`.
> 6. Also, don't forget to check if it succeeded or not.

#####5.2.6.2 mv
The `mv` command has two uses. They are:  
1. Moving files and folders from one place to another  
2. Renaming the files and folders. It is basically moving the files and folders to the same place with different name. Will be clear after we do try it.

Syntax for `mv` command is similar to that of `cp` command.  
`mv SOURCE DESTINATION`  

Example:  
```shell
user@debian:~$ cd
user@debian:~$ mv file1 new_folder/sub_folder/last_folder
```

Now if you check the files in home folder with `ls`, you will see that it has been moved.

Example of renaming using mv:  
Suppose, the current `new_folder` is not new anymore and you want to rename it to `old_folder`. Command: `mv new_folder old_folder`. List the directories to check the effect.

####5.2.7 Deleting files and directories - rm & rmdir

1. Change your working directory to the `last_folder`.
2. List the files there. You see there is a file named `file1` that we moved from home directory to this directory in previous section.
3. Delete this file. `rm file1`
4. Check for confirmation.  
5. Next come back to the home directory and delete the `old_folder`. `rm old_folder`. Doesn't work. `rmdir old_folder`. Doesn't work. Reason, the folder is not empty. Change to `old_folder` and delete everything inside it...
...
...
...
..

####5.2.8 Displaying the contest of a file in screen

#####5.2.8.1 Clear screen
Command: `clear`
Shortcut: Ctrl+l

#####5.2.8.2 cat
The `cat` command is used to display the content of a file on the screen.
```shell
user@debian:~$ cat /proc/cpuinfo
```

#####5.2.8.3 less
`less` command is used to display the content of the file onto the screen a page at a time.
```shell
user@debian:~$ less /proc/cpuinfo
```

#####5.2.8.4 head
By default the `head` command writes the first ten lines of a file to the screen. You can specify the number of lines you want to display by passing the number as an option. Eg:  
```shell
user@debian:~$ head /proc/cpuinfo
user@debian:~$ head -5 /proc/cpuinfo
```

#####5.2.8.5 tail
By default the `tail` command prints the last ten lines of a file to the screen. You can specify the number of the lines you want to disply by passing the number as an option. Eg:

```shell
user@debian:~$ tail /proc/cpuinfo
user@debian:~$ tail -15 /proc/cpuinfo
```

`tail` can also be used to follow the changes in a file. Specially useful while following a logfile in live mode.

####5.2.9 Searching the contents of a file
Files can be searched using different methods. Here we will check two methods of searching the content of a file.  

1. **Using the `less` command.**  
Open the `cpuinfo` file using `less`. Think of a string to be searched, we will search for the word **Genuine**.
  
2. **Using the `grep` command**  
First thing, by default `grep` is case sensitive.  
Syntax:  
`grep STRING FILENAME`  

Eg:  
`grep Genuine /proc/cpuinfo`  

To ignore the case sensitivity, you can use `-i` option.  
Example:  
`grep -i genuine /proc/cpuinfo`


####5.2.10 Finding files in the system - find
The `find` command in Linux can be used to find files from the command line. It has many features and options. But we will go through only the basic and useful ones. More advanced use of `find` command can be finding files with various criterias such as permissions, user ownerships, modifications, size etc.  
Basic Syntax of `find` command:  
`find location criteria search-termn`  

The `find` command without any arguements will list out all the files in the current directories as well as the subdirectories in the current directory.
#####5.2.10.1 Searching for files in current directory
Let us change to the folder `/usr/share/`. If you list files in that directory with `ls` command you will see lots of files and folders there. To search manually in this folder would be a really difficult task. Let us find something called `icon`. The command would be:  
`find . -name icon` or `find . -name "icon"`  

* Suppose we need to find files with `.png` extensions only. We can use wildcards too. Example:  
`find . -name "*.png"`  

* Suppose we are not sure if the file name has uppercase or lowercase. We can ignore the case using `-iname` option. Example:  
`find . -iname "*.PNG"`  

#####5.2.10.2 Searching for files in another directory different than current directory
All we need to do is give the absolute path. Let us move to our `home` directory and search for the same files as in previous section.  
Examples:  
`find /usr/share/ -name icon`  
`find /usr/share/ -name "*.png"`

#####5.2.10.3 Finding and deleting the files
1. To find and remove a single file, let us create a file called `remove.txt` in our home directory. The command would be  
`find . -name "remove.txt" -exec rm -f {} \;`

2. To find and remove multiple files, let us create a few files named `file1.txt`, `file2.txt`, `file3.txt` and `file4.txt`. The command would be  
`find . -name "*.txt" -exec rm -f {} \;` 

#####5.2.10.4 Finding files of specific size
* Files of size 50MB  
`find . -size 50M`

* Finding and deleting files of 50MB
`find . -size 50M -exec rm -rf {} \;`

* Finding files of size greater than 50MB
`find . -size +50M`

* Finding files of size less than 50MB
`find . -size -50M`

* Finding file sof size in between 50MB and 100MB
`find . -size +50M -size -100M`

*Can append the `-exec` on these as required.*   
***Note:** There are lots of other options that can come with find, such as finding files of specific permissions, made by specific user,, made on certain dates, file types etc.*



####5.2.11 Locating executable files associated with given command - which
`which filename`    
Example:  
`which ls`  


####5.2.12 Locating files associated with given command - whereis
Similar to `which` but it locates the binary, source, documentation and manual pages of the command.
Example:  
`whereis ls`  

####5.2.13 Symlinking files - ln
`ln` is a command which makes symlinks (Symbolic Links) of a file, folder from a given path to another path.  
Syntax:  
`ln -s SOURCE TARGET`

Example:  
`ln -s /usr/share/ ~/share`  

Uses:  
Symbolik links have lots of uses. For example, suppose you have a large file that also needs to be in another folder. If you copy that file, it can be a waste of space, so instead of copying the whole file you can just link that file to another folder where it is required. Another example is, there may be a dualboot system and each has its own browser, text editors etc. So instead of setting up and configuring the browsers in each system, the profiles and configurations can just be symlinked to the required folder of another operating system.

####5.2.14 I/O redirections - "<" & ">"
I/O redirection (Input Output Redirection) is a powerful feature used by various commands. The default I/O system are generally Keyboards & Mouse and Display. We have seen various commands print out their output to the display. We can change this behaviour by redirecting the output or many commands to files as well as make the commands take input from different source.  

#####5.2.14.1 Output Redirection - >
Example:  
`user@debian:~$ ls > contents`  

This command redirected the output of the command `ls` to a file called `files.txt`. Generally sing `>` operator overwrites the file. But if you want the contents of the files to be preserved but the new stuffs be appended in the existing contents you need to use the `>>`.  
Example:  
`user@debian:~$ date >> contents`  

This will append the current time and date to the existing file named as `contents`.

#####5.2.14.2 Input Redirection - <
Example:  
```shell
user@debian:~$ wc -l contents
user@debian:~$ wc -l < contents
```
####5.2.14.3 Combining Input Redirection & Output Redirections
Example:   
`user@debian:~$ wc -c < contents > characters`
 
####5.2.15 pipe 
I/O Redirections was to send data to and from the files. Pipe `|` is a method of sending output from one command as input to another command. It is useful for joining lots of small easy commands to perform a large and complex task. Let us take example that we need to find the first 2 files in our folder.  
`user@debian:~$ ls | head -2`  

Another example:  
We need to find the number of folders in our current directory.  
`user@debian:~$ ls -d */ | wc -l`  

Find the fifth file in a directory:  
`user@debian:~$ ls | head -5 | tail -1`


####5.2.16 ifconfig, iwconfig 
The command `ifconfig` is used to configure a network interface in linux. This command without any arguements will show the currently detected network interfaces in your system. 


####5.2.17 history
The `history` command is used to view the history of all the commands that has been entered by the current user in the terminal.  

**Task:**  
* Find the 100th command you entered.  
* Save all the `cd` commands you used to a file named cd_history.



####5.2.18 sed
`sed` is a stream editor. It is useful for editing and filtering the texts from various input streams (files, keystroke, output of another command etc.). Mastering `sed` can be equivalent to mastering a small programming language. Some simple, useful and basic uses of sed are as given below. We can write scripts or programs that will make changes in a file automatically using sed. 

```shell
sed -i "s/..../..../g" filename
sed -i "s/.../..../1" filename
sed -i "s/.../..../3g" filename
sed -i "3s/.../..../" filename

sed -e "s/.../..../g" -e "s/.../..../g" < filename > filename
sed -e "s.../..../g" -e "s/.../..../g" < filename > newfilename
```

####5.2.19 whoami
`whoami`




