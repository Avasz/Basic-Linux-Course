# Chapter 2
## Linux Structure and Installation

By the end of this chapter, you should be able to:  
* Identify Linux Filesystems.
* Identify the difference between partition and filesystems.
* Describe boot process
* Know how to install Linux distribution on a computer (Practical)

###1. Linux Filesystems and Partitions
* **First of all, think of a disk as a cake**

1. Partition is a logical part of the disk. *A slice of a cake would be a partition*
1. Filesystem is method of storing/finding files on a hard disk. *Icing on top of the cake would be filesystem*
1. Partitions in Linux is different from partition in windows.  
	a. They do not have drive letters (C: drive, D: drive) in Linux.


###2. Linux Filesystem in detail.
In Linux systems, files are stored in a standard layout called the Filesystem Hierarchy Standard (FHS). Linux uses '/' (Forward slash character) to separate paths. As mentioned earlier, Linux doesn't have drive letters as in windows. Linux filesystem is case sensitive, for eg: /home is different from /Home, /HOme, /HOME. In fact, all of them are different from one another.  
'/' represents the root of the Linux file systems. Root as in the topmost folder, not Root user. All other folders are organized in heirarchical way inside the '/'. For convinience, Linux file system is usually thought of in a tree structure. A general linux file system layout is shown below:  
![File system tree](./../../Images/Chapter2/filesystem_tree.jpg)    
Depending on distros, there maybe certain changes/difference in the structure of the file system. Some directories may be omitted or be added as per requirement.  

1. The file system tree starts with a '/'. This contans all other directories and files. This is known as *root directory* or *the root* of the file system.  
2. Directories one level below the root directory are preceded by a slash to indicate their position. eg: /etc, /boot, /tmp. 


####2.1 Explanation of Subdirectories of the Root Directory
| Directory | Content |
| --------- | ------- |
| /bin | Contains common programs, shared by the system, system administrator and the users. |
| /boot | Contains the startup files and the kernel that is required by an operating system while booting. |
| /dev | Contains reference to all hardwares in the system. They are represented as files. |
| /etc | System configuration files are stored in /etc. This directory contains data similar to those in Control Panel in Windows. |
| /home | Home directory of common users in the system |
| /lib | Contains library files that are required by programs and users. |
| /lost+found | Every partition contains a lost+found in its root directory. Files saved during failures will be here. |
| /mnt | This is standard mount point for external devices such as DVD-ROM, Camera etc. |
| /opt | Generally contains third party softwares. eg: Viber |
| /proc | Contains information about all system processes. This is a pseudo file system. Eg. It contains information of CPU, Memory etc. in files cpuinfo and meminfo respectively. |
| /root | This is the home directory of Root user. |
| /sbin | Contains programs used by the system and system administrator. |
| /tmp | Temporary space used by system. The files on this directory will be cleaned upon reboot. |
| /usr | Contains all system-wide, read-only files installed by (or provided by) the OS. |
| /var | Storage for all variable and temporary files created by users. Eg. Log files, email queue etc. |


