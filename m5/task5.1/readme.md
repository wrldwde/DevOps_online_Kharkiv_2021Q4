
# TASK4.1
## Workflow:

#####While doing this task, I have reported only main information about the fulfilment of task points: methods and results.
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
`tree -L 2 -P '*.png' (or execute something like `tree -P '*.png' --prune` to show all .png files without non-request directories)


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
</details>






[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>
[task4.1-sql]:<https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m4/task4.1/drugsore_20211130.sql>

