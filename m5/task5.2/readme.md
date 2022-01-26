# TASK5.2
## Workflow:



#### 1)  Let's see and determine what is contained in the /etc/passwd and /etc/group files:
- /etc/passwd: 
![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_1.png)

As we can see, `/etc/passwd`  file contain user's account information stored by 7 fields separated by ':' and contains next information:
	- Username, used when log in, should be between 1 to 32 characters; 
	- Password, an 'x' character indicates that encrypted password is stored in /etc/shadow file;
	- User ID (UID), each user must be assigned a user ID (UID). UID 0 (zero) is reserved for root and UIDs 1-99 are reserved for other predefined accounts. Further UID 100-999 are reserved by system for administrative and system accounts/groups;
	- Group ID (GID), the primary group ID, stored in /etc/group file;
	- User ID info (GECOS), field with user's additional information;
	- Home directory, the absolute path to user's home directory when logged in;
	- Default shell, the absolute path to user's default shell (command interpreter).
Pseudo user accounts created to run certain apps or/and files. For example, `syslog`, `deamon`, `sshd` etc.
![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_2.png)

- /etc/group:
![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_3.png)

`/etc/group` file contain information about user groups stored by 4 fields also separated by ':' and contains next info about groups:
	- Group name, directly name of group;
	- Password, but generally is not used, but useful to implement privileged groups;
	- Group ID (GID), GID for assigning users to group;
	- Group list, list of user names, assigned to group, separated by commas.

#### 2) UID stands for user ID. The UID is the number assigned to each Linux user. This is the user representation in the Linux kernel.  
The UID is used to identify the user on the system and to determine which system resources the user can access. That's why the user id must be unique.

UID could be find in */etc/passwd* on 3-rd field.
command `id` could be used to define current user's UID and GID, or `id *username*` to define *username*'s UID.

Also UID could be changed by `usermod` command:
`usermod -u 1004 user_name`

UID range is an integer from 0 to 65535. Unix-like system reserving some IDs for system needs, as 0 UID and GID for root user and root user's group, 65534 UID and GID used for 'nobody' and 'nogroup', IDs from 1 to 100, 101-499 / 101 - 999 reserved for system needs and vary from OS to OS.


![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_2.png)

#### 3) As mentioned before GID stand for defining Groups in Linux. Users assigned to groups exactly by GID.

GID, like UID, could be find in */etc/passwd* file on 4-th field (the group the user is associated with) and in */etc/group* file on 3-rd field (exactly group's ID).

GID also could be defined as UID by `id` command to find out current user's GID and `id *username*` to define *username*'s GID.


#### 4)Belonging user to the specific group could be determined in /etc/passwd file in GID field or by `groups` command:
```
groups wrldwde 
wrldwde : wrldwde adm cdrom sudo dip plugdev lpadmin lxd sambashare
```

#### 5)New user could be created by executing `adduser`, and then you should specify  details, like Full Name, password, room number, work phone, home phone (GECOS info).  As example:


![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_4.png)

#### 6) To change username or other user's info the `usermod` command is used. For example:
``
sudo usermode -l karakashian danylo
``

UID could be changed using `-u` attribute.

![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_5.png)

#### 7)The */etc/skel* directory contains files and directories that are automatically copied over to a new user’s home directory when such a user is created by the useradd program, depends on */etc/default/useradd* file. skel is derived from the “skeleton”.


![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_6.png)

#### 8) To remove user including home dir and mailbox `userdel` command used:
``
sudo userdel -r <username>
``


![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_7.png)

#### 9) Command `passwd` with keys `-l` and  `-u` used to lock and unlock user accounts:


![Screen8](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_8.png)

#### 10) Command `passwd` with attribute `-d`  deletes user password (make it blank). Attribute `-e` makes password obsolete immediately. As a result, this will force the user to change the password the next time they log in. So, next command was used:
``
sudo passwd -de john
``


![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_9.png)

#### 11) Executed `ls` command to display list of files and directories with extended information:
``
ls -lahi
``


![Screen10](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_10.png)

#### 12) Access rights field contain  9 characters, three groups of three characters: 
`xxxyyyzzz`, where
xxx - set of object owner access rights;
yyy - set of object group access rights;
zzz - set of access rights for others.

For each set, there are three positions for certain access flag:
first character is for `r` - right for read;
second character is for `w` - right for write;
third character is for `x` - right for execute;

Access rights for file could look like this:

`rwxr-xr-x`
where owner could read, write and execute, the group the file belongs to could read and execute and the others could read and execute too.

There are also present `--s` and `--t` flags, which means SUID or SGID bit for first or second group respectively with `--s` flag and sticky-bit with `--t` bit.

SUID flag means that the id of the user from which it is launched is replaced by the id of the owner of the file. In effect, this allows regular users to run programs as root;
SGID flag means the same as SUID, but the only difference is that the user is considered a member of the group the file is associated with, not the groups to which they actually belong. If the SGID flag is set on a directory, all files created in it will be associated with the group of the directory, not the user. This behavior is used to organize public folders;
Sticky-bit is also used to create shared folders. If set, users can only create, read, and execute files, but cannot delete files owned by other users.

Also access rights could be represented by octal:
0 - none (---)
1 - execute-only (--x)
2 - write (-w-)
3 - execute and write (-wx)
4 - read-only (r--)
5 - read and execute (r-x)
6 - read and write (rw-)
7 - read, write and execute (rwx)


#### 13)Firstly defined owner rights, then group rights and others for the last.

#### 14)Command `chmod` is used to change owner or access rights
`chmod <new-owner> <file-name>`
`chmode -v 777 <file-name>`

![Screen11](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_11.png)

#### 15)Octal representation was considered in point 12.
The `umask` command sets the permissions mask for new files and directories. When creating any file, the operating system requests a permissions mask and calculates the mask based on it. The default mask is 0002 (the firs '0' is deprecated). Further, the numbers are similar to the access rights in Linux: the first is the owner, the second is the group and the third is others. It turns out that the mask contains permissions that will not be set for the file. Therefore, the default permissions for a file will be 666 - 002 = 664, and for a directory - 777 - 002 = 775.

#### 16)Sticky bit and UID and GID substitutions was considered in point 12.


![Screen12](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_12.png)


#### 17)Attribut `x` should be present for command scripts, because it right to execute file.
But file also have other attributes:
**a - append only:** this attribute allows a file to be added to, but not to be removed. It prevents accidental or malicious changes to files that record data, such as log files.
**c - compressed:** it causes the kernel to compress data written to the file automatically and uncompress it when it’s read back.
**d - no dump:** it makes sure the file is not backed up in backups where the dump utility is used
**e - extent format:** it indicates that the file is using extents for mapping the blocks on disk.
**i - immutable:** it makes a file immutable, which goes a step beyond simply disabling write access to the file. The file can’t be deleted, links to it can’t be created, and the file can’t be renamed.
**j - data journaling:** it ensures that on an Ext3 file system the file is first written to the journal and only after that to the data blocks on the hard disk.
**s - secure deletion:** it makes sure that recovery of a file is not possible after it has been deleted.
**t - no tail-merging:** Tail-merging is a process in which small data pieces at a file’s end that don’t fill a complete block are merged with similar pieces of data from other files.
**u - undeletable:** When a file is deleted, its contents are saved which allows a utility to be developed that works with that information to salvage deleted files.
**A - no atime updates:** Linux won’t update the access time stamp when you access a file.
**D - synchronous directory updates:** it makes sure that changes to files are written to disk immediately, and not to cache first.
**S - synchronous updates:** the changes on a file are written synchronously on the disk.
**T - and top of directory hierarchy:** A directory will be deemed to be the top of directory hierarchies for the purposes of the Orlov block allocator.

 To get file attributes use the command `lsattr`:
 

![Screen13](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.2/Screenshots/Screen_13.png)

[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>
