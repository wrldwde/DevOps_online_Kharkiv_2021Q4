
# TASK5.1
## Workflow:

##### While doing this task, I have reported only main information about the fulfilment of task points: methods and results.
<details>
<summary> PART1 </summary>
<br>
  
  
1)  To log in as root, executed next:
  
`sudo su`

  
2) `passwd` command used for managing  users' passwords (changing, deleting, setting expiration date and status-check). The command works with the following system files:

/etc/passwd - user accounts information    
/etc/shadow - secure user accounts information
/etc/pam.d/passwd - PAM configuration for passwd

  
3) To determine users in host system could be used next commands:

`cat /etc/passwd` or `less` - shows *passwd* file which contain users name, password (stored in *shadow*), UID,  GID, GECOS (full user name), home dir, login shell
`getent passwd` - also show *passwd* content
`last -a` and `lastlog` - show users and their last login

Commads, also used to determine users and information about them:
`w`
`who`
`finger`

  
![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_1.png)

  
4) User personal information changed with following command:
  
`chfn` - changing personal information, displayed by `finger` command, as example

  
![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_2.png)


5)Both `man` and `info` commands are used as follows:

`man 'command'` and `info 'command'`

Examples:

`finger -l wrldwde` - Produces a multi-line format displaying all of the information described for the -s option as well as the user's home directory, home phone number, login shell, mail status, and the contents of the files “.plan”, “.project”, “.pgpkey” and “.forward” from the user's home directory.

`finger -p wrldwde` - Prevents the -l option of finger from displaying the contents of the“.plan”, “.project” and “.pgpkey” files.

`w -i` - Display IP address instead of hostname for from field.

`w wrldwde` - Display IP address instead of hostname for from field.

  
5) `more`  is  a filter for paging through text one screenful at a time. `less` provides `more` emulation plus extensive enhancements.

Unlike `more`, `less` provides reading files without clogging a terminal.


![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_3.png)


7)Added plans to ~/.plan for *wrldwde* user, executed `finger wrldwde` to make sure in changes.


![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_4.png)


8) Next command executed to list the contents of the home dir:
`ls -alh --group-directories-first`


![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_5.png)



</details>

<details>
<summary>PART2</summary>
<br>


1) Executed following command to show *wrldwde* home tree where files have .png file format with the second nesting level:

`tree -L 2 -P '*.png' `(or execute something like `tree -P '*.png' --prune` to show all .png files without non-request directories)


![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_6.png)


2)Command `file` could be used to determine file type.

`file .bashrc`
`file Изображения/Снимок\ экрана\ от\ 2021-12-13\ 23-56-43.png `
`file DevOps_online_Kharkiv_2021Q4/DevOps_online_Kharkiv_2021Q4/m4/task4.1/readme.md`


![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_7.png)


3)Relative and absolute paths to go back to my home dir looks like:

Relative
`cd` or `cd ~` or `cd  $home`

Absolute
`cd /home/wrldwde`


  
4)`ls` command executing example was demostrated on Part 1 point 8. *-a* option show all files and directories including starting with '.'. *-l* option show files and dirs as a list.


  
5)Following commands have been executed for this point:

`mkdir task5.1_subdir`
`tree -dL 1 > task5.1_subdir/drinfo.txt`
`cat task5.1_subdir/drinfo.txt `
`cat task5.1_subdir/drinfo.txt `
`cp task5.1_subdir/drinfo.txt  /home/wrldwde/dirinfo_abs.txt`
`rm -rI task5.1_subdir/`
`rm dirinfo_rel.txt dirinfo_abs.txt `


![Screen8](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_8.png)


  
6) Following commands have been executed for this point:

`mkdir test` 
`cp .bash_history test/labwork2`
`cd test`
`ln -P labwork2 hardlink`
`ln -s labwork2 softlink`
`less softlink`
`less labwork2`
`mv hardlink hard_link_labwork2 && mv softlink symb_link_labwork2`
`rm labwork2`
`less hard_link_labwork2`
`less symb_link_labwork2`


![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_9.png)


![Screen10](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_10.png)


About hard and soft links,  soft links (or symbolic) contain the address of the desired file on your filesystem. When you try to open such a link, the target file or folder is opened. Its main difference from hard links is that when the target file is deleted, the link will remain, but it will point to nowhere, since the file actually no longer exists. They can refer to files and directories, they can refer to other disk partitions and contain only the file name, not its contents. 
Hardlink is implemented at a lower level in the file system. The file is located only in a certain place on the hard disk. But this location can be referenced by multiple links from the filesystem. Each of the links is a separate file, but they lead to one section of the hard drive. They work only within the same file system, they cannot refer to directories, and you can also move and rename and even delete a file without harming the link. 


  
7) Followin `locate` command have been executed to find 'squid' and 'traceroute' sequences:

`locate -A squid`
`locate -A traceroute`


![Screen11](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_11.png)


  
8)To determine partitions in system could be used `df` command:

`df -Th`


![Screen12](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_12.png)


  
9) To count lines containing "sudo*" sequence in *.bash_history* file we can use next command:

`grep -c "sudo*" .bash_history`


![Screen13](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_13.png)


  
10)To find all files in */etc/* dir, we can use following command:

`cd /etc/`
`sudo find -type f -name "*host*"`


![Screen14](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_14.png)


11)Following command has been executed for this point:

`ls -al | grep "ss"`


![Screen15](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_15.png)


12)To organize a scree-by-screen print of the contents of */etc* dir has been executed following:

`ls -alh | less`


![Screen16](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_16.png)


13)One of the basic features of  LinuxOS is that it abstracts the handling of devices. All hardware devices look like regular files. Every device in the system is represented by a device special file, located in /dev/ directory. 
Linux supports three types of hardware device: character, block and network. Character devices are read and written directly without buffering (stream R-W).Block devices can only be written to and read from in multiples of the block size, typically 512 or 1024 bytes.  Network devices are accessed via the BSD socket interface.


![Screen17](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_17.png)


14)There are 7 types of file in Linux:
Regular files, denoted with "-", are ordinary files on a system that contains programs, texts, or data. 
Directory files, denoted with "d", the sole job of directory files is to store the other regular files, directory files, and special files and their related information.
Block files, denoted with "b", block files act as a direct interface to block devices hence they are also called block devices.
Character files, denoted with "c", provide a serial stream of input or output and provide direct access to hardware devices.
Pipe files, denoted with "p", sends data from one process to another so that the receiving process reads the data first-in-first-out manner.
Symbol links files, denoted with "l", is a type of file in Linux which points to another file or a folder on your device.
Socket files, denoted with "s", is a special file that is used to pass information between applications and enables the communication between two processes. 

We can filter `ls` output with denoting by following commands, using `grep`:

`ls -la | grep ^-`
`ls -la | grep ^d`
`ls -la | grep ^b`
`ls -la | grep ^c`
`ls -la | grep ^p`
`ls -la | grep ^l`
`ls -la | grep ^s`

We can use `file` command to check the file type:

`file /dev/sda`
`file /dev/zfs`


![Screen18](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_18.png)


15)To see last 5 used directories in etc/ used following command:

`ls -ltr | tail -n 5`


![Screen19](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.1/screenshots/Screenshot_19.png)


</details>






[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>


