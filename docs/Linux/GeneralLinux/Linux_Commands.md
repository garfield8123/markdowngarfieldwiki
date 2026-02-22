# Linux Commands

## Common Standard I/O Redirections

| Task | Command syntax |
| --- | --- |
| Send stdout to a file | command > file |
| Send stderr to file | command 2> file |
| Send stdout and stderr to file | command > file 2>&1 |
| Read stdin from a file | command < file |
| Read stdin from file.in and send stdout to file.out | command < file.in > file.out |
| Append stdout to the end of a file | command >> file |
| Append stderr to the end of a file | command 2>> file |
| Append stdout and stderr to the end of a file | command >> file 2>&1 |
| Read stdin from the keyboard until the character c | command <<c |
| Pipe stdout to command2 | pipe |
| Pipe stdout and stderr to command2 | command 2>&1 pipe |

## Store lines until type zz

```
cat <<ZZ > input.txt

```

## Store messages in file

```
find / -name COPYING -print 2> finderr

find / -name COPYING -print2> /dev/null

```

/dev/null = bit bucket (Great bit bucket in the sky): Simply discards whatever it receives.

## Essential Linux Commands

| Command Name | Action |
| --- | --- |
| Finding help and abbreviations |  |
| apropos | Finds online manual pages for a specified keyword |
| info | Displays online help information about a specified command |
| man | Displays online help information |
| whatis | Searches for complete words only and finds the online manual pages |
| alias | Defines an abbreviation for a long command |
| type | Shows the type and location of a command |
| unalias | Defines an abbreviation defined with alias |
| Managing Files and directories |  |
| cd | Changes the current directory |
| chmod | Changes file permissions |
| chown | Changes the file owner and group |
| chgrp | Changes the file group |
| chage | changes user permissions |
| cp | Copies files |
| ln | Creates symbolic links to files and directories |
| ls | Displays the contents of a directory |
| mkdir | Creates a directory |
| mv | Renames a file and moves the file from one directory to another |
| mount | mount device-name mount-point |
| rm | Deletes files |
| rmdir | Deletes directories |
| pwd | Displays the current directory |
| touch | Updates a file's time stamp |
| Finding Files |  |
| find | Finds files based on specified criteria, such as name and size |
| locate | Finds files by using a periodically updated filename database. (The database is created by the updateb program) |
| whereis | Finds files based in the typical directories where executable (also known as binary) files are located |
| which | Finds files in the directories listed in the PATH environment variable |
| Processing Files |  |
| cat | Displays a file in standard output (can be used to concatenate several files into one big file) |
| cut | Extracts specified sections from each line of text in a file |
| dd | Copies blacks of data from one file to another (used to copy data from devices) |
| diff | Compares two text files and finds any differences |
| expand | Converts all tabs to spaces |
| file | Displays the type of data in a file |
| fold | Wraps each line of text to fit a specified width |
| grep | Searches for regular expressions in a text file |
| less | Displays a text file one page at a time (Go backward by pressing b) |
| lpr | prints files |
| more | Displays a text file one page at a time (goes forward only) |
| nl | Numbers all nonblank lines in a text file and prints the lines to standard output |
| paste | Concatenates corresponding lines from several files |
| patch | Updates a text file by using the differences between the original and revised copies of the file |
| sed | Copies a file to standard output while applying specified editing commands |
| sort | Sorts lines in a text file |
| split | Breaks up a file into several smaller files with specified sizes |
| tac | Reverses a file (last line first and so on) |
| tail | Displays the last few lines of a file |
| tr | Substitutes one group of characters for another throughout a file |
| uniq | Eliminates duplicate lines from a text file |
| wc | Counts the number of lines, words, and chracters in a text file |
| zcat | Displays a compressed file (after decompressing) |
| zless | Displays a compressed file one page at a time (Go backward by pressing b) |
| zmore | Displays a compressed file one page at a time |
| Archiving and Compressing files |  |
| compress | Compresses files |
| cpio | Copies files to and from an archive |
| gunzip | Decompresses files compressed with GNU ZIP (gzip) |
| gzip | Compresses files by using GNU Zip |
| tar | Creates an archive of files in one or more directories (originally meant for archiving on tape) |
| uncompress | Decompresses files compressed with compress |
| Managing files |  |
| bg | Runs an interrupted process in the background |
| fg | Runs a process in the foreground |
| free | Displays the amount of free and used memory in the system |
| halt | Shuts down Linux and halts the computer |
| kill | Sends a signal to a process (usually to terminate the process) |
| ldd | Displays the shared libraries needed to run a program |
| nice | Runs a process with a lower priority (referred to as nice mode) |
| ps | Displays a list of running processes |
| printenv | Displays the current environment variables |
| pstree | Shows parent-child process relationships |
| reboot | Shuts down Linux and then restarts the computer |
| shutdown | Shuts down Linux |
| top | Displays a list of the most processor - and memory-intensive processes |
| uname | Displays information about the system and the Linux kernel |
| Managing users |  |
| chsh | Changes the shell (Command interpreter) |
| groups | prints the list of groups that include a specified user |
| id | Displays the user and group ID fr a specified username |
| passwd | changes the password |
| su | Starts a new shell as anther user (the other user is assumed to be root when the command is invoked without any argument) |
| Managing the file system |  |
| df | Summarizes free and available space in all mounted storage devices |
| du | Displays disk-use information |
| fdformat | Formats a floopy disk |
| fdisk | Paritiions a hard drive |
| mkfs | Creates a new file system |
| mknod | Creates a device file |
| mkswap | Creates a swap space for Linux in a file or a hard drive partition |
| mount | Mounts data a device (Such as a CD-ROM) on a directory in the file system |
| swapoff | Deactivates a swap space |
| sync | Writes buffered (saved in memory) data to files |
| tty | Displays the device name for the current terminal |
| umount | Unmounts a device from the file system |
| Displays dates and times |  |
| cal | Displays a calendar for a specified month of year |
| date | Displays the current date and time or sets a new date and time |
| uptime | Summary of the system's state |
| vmstat | Summary information about overall system usage (vmstat 5 8) |
| hdparm | /sbin/hdparm -t shows rate at which data is read from the disk into buffer in memory |

### Kill command

```
kill <pid>
kill -9 <pid>

```

### date command

```
date 123121302023
#MonthDateTime24hrYear

```

### number of processes

```
ps -ax | wc -l

```

### Substituing/deleting characters

```
tr -d '\015' < filename.dos > filename.linux

```

\015= code for carriage-return charcter in octal notation
dos files to linux files using carriage-return replacement

### Splitting file into smaller files

```
split -b 9999k hugefile.tar part.a*

```

splits hugefile.tar to part.aa, ....

### TOP Command Column

| Heading | Meaning |
| --- | --- |
| PID | Process ID of the process |
| USER | Username under which the rocess is running |
| PR | Priority of the process |
| NI | Nice value of the process. The value ranges from -20 (highest priority) to 19 (lowest priority), and the default is 0. (The nice value represents the relative priority of the process: The higher the value, the lower the priority and the nicer the process, because it yeilds to other processes) |
| VIRT | Total amount of virtual memory used by the process, in kilobytes |
| RES | Total physical memory used by a task (typically shown in kilobytes, but an m suffix indicates megabytes) |
| SHR | Amount of shared memory used by the process |
| S | State of the process (S for sleeping, D for unterruptible sleep, R for running, Z for zombies -- processes that should be dead but are still running -- and T for stopped) |
| %CPU | Percentage of CPU time used since the last screen update |
| %MEM | Percentage of physical memory used by the process |
| TIME+ | Total CPU time the process has used since it started |
| COMMAND | Shortened form of the command that started the process |

### vmsat utility command options

| Field Name | Description |
| --- | --- |
| procs | Number of processes and their types: r = processes waiting to run, b = processes in uninterruptible sleep, and w = processes swapped out but ready to run |
| memory | Information about physical memory and swap-space usage (all numbers in kilobytes): swpd = virtual memory used, free = free physical memory, buff = memory used as buffers, and cache = virtual memory that's cached |
| swap | Amount of swapping (the numbers are in kilobytes per second): si = amount of memory swapped in from disk, and so = amount of memory swapped to disk |
| io | Information about input and output (The numbers are in blocks per second, where the block size depends on the disk device) bi = rate of blocks sent to disk, and bo = rate of blocks received from disk |
| system | Information about the system: in = number of interrupts per second (Including clock interrupts), and cs = number of context switches per seconds -- how many times the kernel changed which process was running |
| cpu | Percentages of CPU time used: us = percentage of CPU time used by user processes, sy = percentage of CPU time used by system processes, id = percentage of time CPU is idle, and wa = time spent waiting for input or output (I/O) |

## sed, awk, and paste

```
sed 's/:219\./:260./'

```

finds :219. ad changes it with :260.

```
sed 's/:219./:260./'

```

finds :219 ad changes it with 260.