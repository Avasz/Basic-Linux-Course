#Chapter 4- Finding Linux Documentations

We will learn about various ways of finding inbuilt as well as some third party documentations for Linux & Linux Commands. Documentations is a key factor for success of any projects, Linux is no different. Without a proper, understandable and good documentation no projects can succeed. Documentation is required for developers themselves as well as for others to take reference. By the end of this chapter, you should be able to:  
* Use different sources of documentations
* Use the **man pages**
* Use the **help** command and **--help** options.
* Use other documentation sources.  

###4.1 Document Sources
No matter what your expertise level is, you do require documentations as you may not always know about all the programs and utilities in Linux Operating System. Time to time you need to consult the manuals of the tools you are using regularly. Some of important Linux documentation sources that can help you are:
1. The **man pages**. (Inbuilt)  
2. The **--help** command. (Inbuilt)  
3. Other third party document sources. eg: [The Linux Documentation Project, TLDP](http://tldp.org)  

###4.2 The man pages

The **man pages** are mostly used documentation source in Linux. The word **man** is short form of Manual, hence **man pages** are Manual pages. So, as the name suggests, **the man pages** contains of manual of most of the Linux tools and most of the time it comes pre-installed in Linux distros.  
The syntax for opening the man page is: "**man toolname**".   
eg: man cp, man cd, man mkdir etc.  

You will be presented with detailed description of the tool you have requested, provided it is a valid tool and man pages exists for it.  

####4.2.1 Navigating man pages
Now that you have opened the man page, you may be wondering how to navigate around it. If you are familiar with the **less** command or **vim** editor then it should be easy for you (If you are not, do not worry, you will learn about them later). You can use the standard arrow keys to move up and down, similary the keys 'j' & 'k' can be used for the same too. The advantages of using 'j' and 'k' is that you do not need to move your hand from the home row of keyboard to the arrow buttons and vice versa every time. A few important and useful navigation methods are listed in the table below:

| Action | Shortcuts/Key combinations |
| ------ | -------------------------- |
| move one line up | Up arrow key / k |
| move one line down | Down arrow key / j |
| move to bottom of the man pages | End / shift+g (G) |
| move to top of the man pages | Home / gg |
| page down | PgDn / Ctrl+F |
| page up | PgUp / Ctrl+B |
| half page down | Ctrl+D |
| half page up | Ctrl+u |
| search for a string | /string. eg: if you need to search for string 'hello, then /hello |
| next matching search pattern | n |
| previous matching search pattern | N |
| quit | q |

Fore more about man pages you can do: man man ;)

###4.3 The --help option
Man pages covers very detailed information about each and every arguements and parameters of the tool. If that seems too long then there is a help option available for most of the commands. Help has a short description of the command, its syntax and its arguements. It can be viewed by passing **-h** or **--help** option to the command. For eg: cd --help, ls --help. Help can be used for quick reference and it also displays informations faster than the man pages.

###4.4 The GNU Info System
In addition to man & help, Linux also has the GNU project's standard documentation format called **info**. It can be called an alternative to the man pages. It resembles the man pages in many ways, however there are a few differences such as navigating around, and also it is more free-form and supports linked sub-sections.

###4.5 Other document sources
The documentation of tools and softwares are not limited to only man, info and help. There are other sources of Linux documentations like the documentations of the package itself, Graphical Help System, Online resources like wiki, forums etc. Gnome-help is desktop help system for the GNOME Environment, similarly KDE has khelpcenter. The package documentation are generally placed in /usr/share/doc directory which contains subdirectory of each packages. For online resources, some of really good resources are:  [The Linux Documentation Project, (TLDP), http://tldp.org](http://tldp.org), [Ubuntu Help, http://help.ubuntu.com](http://help.ubuntu.com), [LinuxCommand.org](http://linuxcommand.org/tlcl.php) etc.

