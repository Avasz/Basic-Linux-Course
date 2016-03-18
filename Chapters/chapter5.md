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
```
bishnu@debian:~/Documents$ _ 
root@debian:~/usr/share# _
```


For explaining the prompt we will separate each section of the prompt into different parts.  
1. bishnu: This is the name of the current user you are logged in as. In the second line, it is logged in as **root**.  
2. debian: This is the hostname of the computer you had set during the installations. This can be changed if required. It means, other computers in your network will know your machine with this name.  
3. /Documents or /usr/share: This is the path of your current working directory. You can verify it with the command **pwd**.  
4. $ or #: This ends the prompt. **'$'** means the user is logged in as normal user. And, **'#'** means the user is logged in as the root user.  
5. The space after this is the place for us to enter commands.  

If you want to operate only in Command Line and turn of the graphical desktop environment, then you can issue either of these commands:  
1. sudo systemctl stop gdm (For GNOOME)  
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

1. whoami  
2. pwd  
3. cd  
4. mkdir  
4. ls
5. cat  
6. echo  
7. rmdir
8. cp
9. mv
10. reboot
11. poweroff, halt
12. which
13. whereis
14. symlink
15. I/O redirection "< & >"
16. Pipes
17. locate (updatedb)
18. find
19. wildcards
20. less
21. tail
22. head
23. touch
24. rm , rm -i, rm -f
25. dpkg, apt-get, apt-cache
26. ifconfig
27. iwconfig
28. grep
29. sed
30. history

####1. Listing Files and Folders - ls
ls command is used for listing the files and directories. Just typing the **ls** command in your prompt will display the files and directories in your current folder. You can type full path of the folder you want to view.
eg:
```
user@debian:~$ ls
Documents	Downloads	Music	Public
```

Some useful options of **ls** command:    
* ls -a    
	This displays all the files and directories, even the hidden ones.
eg:
```
user@debian:~$ ls -a
. .. .config .fonts Documents Downloads Music Public
```

* ls -l  
	This displays long list
```
user@debian:~$ ls -l
total 16
drwxr-xr-x 2 avasz avasz 4096 Mar 18 11:11 Documents
drwxr-xr-x 3 avasz avasz 4096 Mar 18 11:11 Downloads
drwxr-xr-x 2 avasz avasz 4096 Mar 18 11:11 Music
drwxr-xr-x 3 avasz avasz 4096 Mar 18 11:11 Public
```

* Do it yourself: combine the options l & a in same command and find the difference.

####2. Making Directories - mkdir
**mkdir** command is used to make directories. 
Syntax:  
```mkdir [OPTIONS]... DIRECTORY...
```

**Example:**  
```
user@debian:~$ mkdir New_Directory
```
After that you can test if the new directory has been created or not by using the **ls** command we learnt earlier.  

One important option that can be used with **mkdir** is the **-p** option. Generally, if you want to create subdirectories in a directory that doesn't exist then **mkdir** will return an error. But if you use **-p** option, then it will create the parent directories as necessary. Example:
```
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













