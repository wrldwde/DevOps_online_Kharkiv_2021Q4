# TASK5.3
## Workflow:


### PART 1
#### 1)  While process exist, it’ll be in one of the five possible states:

-   Running or Runnable ( R );
-   Uninterruptible Sleep ( D );
-   Interruptable Sleep ( S );
-   Stopped ( T );
-   Zombie ( Z ). 

We can see the list of processes and their status by `ps` command (`top`, `htop` etc). Also we could get states' description in `ps` manual:


![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_1.png)

States column in `ps aux` output:


![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_2.png)

#### 2) `pstree` shows processes by tree view:


![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_3.png)

#### 3) Linux user-space programs cannot access the system kernel directly. So, to obtain information from the kernel, several special directories were created with the help of which any program or user can obtain information about the state of the computer and the kernel. This is the proc and sys virtual file systems.

From these folders you can get any information about your system. For example, how much swap memory is currently in use, how large the processor cache is, what kernel modules are loaded, how many disks or partitions are available, and so on. All this can be obtained as plain text form from the proc linux directory.


![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_4.png)

#### 4) Info about CPU can be obtained from `'/proc/cpuinfo'` file:


![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_5.png)

#### 5) To get a list of processes including info about process owner, he arguments with which the process was launched for execution, the group owner of this process, etc, we could use `ps` command with `-au` options


![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_6.png)

#### 6) All kernel processes are born by `kthreadd` (PID = 2), so we can see all kernel processes by executing `sudo pstree 2` command, where `2` is `kththreadd` PID:


![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_7.png)

User processes are all processes except kernel processes, so we can limit the `ps` command output:
`ps -N --ppid=2 --pid=2`


![Screen8](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_8.png)

#### 7) Processes list with info about status:
`ps -aux`


![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_9.png)

There are also present Running  and Idle kernel thread processes.

#### 8) To list processes of specific user we need to add `-u` option with a required *username*:
`ps -au wrldwde`


![Screen10](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_10.png)

#### 9) From `man ps` page we find out, that we can use `pgrep`, `pstree`, `top` and `proc` command to get some info about processes:


![Screen11](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_11.png)

#### 10) `top` command display processes info in real-time:


![Screen12](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_12.png)

#### 11) To show `top` output for specific user we should add `-u` option and required username:
`top -u wrldwe`


![Screen13](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_13.png)

#### 12)To control `top` output, there are set of interactive commands: 

**d** | **s** :_Change-Delay-Time-interval_
              You will be prompted to enter the delay time, in seconds,
              between display updates.
**?** | **h** :_Help_
              There are two help levels available.  The first will
              provide a reminder of all the basic interactive commands.
**W** :_Write-the-Configuration-File_
              This will save all of your options and toggles plus the
              current display mode and delay time.           
**Y** :_Inspect-Other-Output_
              After issuing the 'Y' interactive command, you will be
              prompted for a target PID.  Typing a value or accepting
              the default results in a separate screen.  That screen can
              be used to view a variety of files or piped command output
              while the normal top iterative display is paused.
**f** :_Fields-Management_
                 This key displays a separate screen where you can
                 change which field is used as the sort column, among
                 other functions.  This can be a convenient way to
                 simply verify the current sort field, when running top
                 with column highlighting turned _Off_.
**L** :_Locate-a-string_
           You will be prompted for the case-sensitive string to locate
           starting from the current window coordinates.  There are no
           restrictions on search string content.
**z** :_Color/Monochrome_ toggle
              Switches the 'current' window between your last used color
              scheme and the older form of black-on-white or white-on-
              black.           
**V** :_Forest-View-Mode_ toggle
              In this mode, processes are reordered according to their
              parents and the layout of the COMMAND column resembles
              that of a tree.

There are separate item (point 4) in manual `man top` page. Also, as mentioned, `h` or `?` commands could be used to show some interactive commands.


#### 13) Sorted by:
- Name (command name):


![Screen14](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_14.png)

![Screen15](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_15.png)

- CPU usage:


![Screen16](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_16.png)

![Screen17](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_17.png)

- Memory usage:


![Screen18](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_18.png)

![Screen19](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_19.png)

#### 14) Processes priority concept, like in other OSs,in Linux determines how much CPU or processor time is allocated to execute task. 
The nice (priority) value of a process can have a range between -20 (highest priority) to +19 (lowest priority); by default, its value is 0.
Also, regular user could decrease process nice value, but only superuser could increase niceness.

To start process with niceness other than default, you can use `nice` command:
`nice -n 19 apt get *pkgname*`

To change nice value of existing process, we should use `renice` command with PID of required process:
`sudo renice -n -2 -p 13919`


![Screen20](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_20.png)

![Screen21](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_21.png)

#### 15) To change process priority from `top` utility, we can use `r` interactive command:


![Screen22](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_22.png)

![Screen23](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_23.png)

![Screen24](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_24.png)

#### 16) `kill` command is used to terminate processes manually by sending signal to a process. It uses PID as identifier:
`kill 31900`


![Screen25](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_25.png)

To display all the available signals we can use `-l` option:
`kill -l`


![Screen26](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_26.png)

```
SIGTERM - default signal to terminate process;
SIGKILL - terminate process if SIGTERM is ignored;
SIGSTOP - pausing process;
SIGCONT - continue process;
```


![Screen27](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_27.png)

![Screen28](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_28.png)

![Screen29](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_29.png)

#### 17) Brief commands descriptions:
`jobs` - shows list of jobs in current session shell;
`fg` - brings the process from background to foreground;
`bg` - brings the process from foreground to background;
`nohup` - allows to continue executing process ignoring SIGHUP signals, like closing SSH connection or logout.


![Screen30](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m5/task5.3/Screens/S_30.png)

### PART 2
#### 1)
