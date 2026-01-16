# Linux Directory

## Linux File Types

| Label | Type | Description |
| --- | --- | --- |
| - | Regular File | Item is an everyday file, such as a text file or program |
| B | Block device | Item is a driver (control program) for a storage medium, such as a hard drive or DVD drive |
| C | Character device | Item is a driver (Control program) for a piece of hardware that transmits data, such as a modem |
| D | Directory | The item is a container for files, also referred to as a folder |
| L | Link | The item is a link to another file. The item doesn't exist as a spearate file, but is a pointer to another file |

## Contents of Linux

| Directory | Contains |
| --- | --- |
| /bin | Essential Commands that everyone needs to use at any time |
| /boot | The information that boots the machine, including your kernel |
| /dev | The device drivers for all the hardware that your system needs to interface with |
| /etc | The configuration files for your system |
| /home | The home directories for each of your users |
| /lib | The libraries or code that many programs (and the kernel) use |
| /media | A spot where you add temporary media, such as DVDs and USB sticks; not all distributions have this directory |
| /mnt | A spot wher you add extra file system components such as networked drives and items you aren't permantely adding to your file system but that aren't as temporary as DVDs and USB sticks |
| /opt | The location that some distributions use for isntalling new software packages, such as word processors and office suites |
| /proc | Current seetings for your kernel (operating system) |
| /root | The superuser (root user's) home directory |
| /sbin | The commands the system administrator needs access to |
| /srv | Data for your system's services (the programs that run in the background) |
| /sys | Kernel information about your hardware |
| /tmp | The place where everyone and everything stores temporary files |
| /usr | A complex hierarchy of additional programs and files |
| /var | The data that changes frequently, such as log files and your mail |
| /etc/shadow | File that contains all users and stuff |
| /etc/sudoers | File that contains all users with sudo permission |
| /etc/fstab | File that shows the mount-point |
| /etc/passwd | password encrpted of all users |

## Directories in /proc

| File Name | Content |
| --- | --- |
| /proc/acpi | Information about Advanced Configuration and Power Interface (ACPI) -- an industry, standard interface for configuration and power management on laptops, desktops, and servers |
| /proc/bus | Directory with bus-specific information for each bus type, such as PCI |
| /proc/cmdline | The command line used to start the Linux kernel (scuh as ro root=LABEL = /rhgb) |
| /proc/cpuinfo | Information aout the CPU (the microprocessor) |
| /proc/devices | Available block and chracter devices in your system |
| /proc/dma | Information about DMA (direct memory access) channels that are used |
| /proc/driver/rtc | Information about the PCs real time clock (RTC) |
| /proc/filesystems | List of supported file systems |
| /proc/ide | Directory containing information about IDE devices |
| /proc/interrupts | Information about interrupt request (IRQ) numbers and how they're used |
| /proc/ioports | Information about input/output (I/O) port addresses and how they're used |
| /proc/kcore | Image of physical memory |
| /proc/kmsg | Kernel messages |
| /proc/loadavg | Load average (Average number of processes waiting to run in the past 1,5,and 15 minutes) |
| /proc/locks | Current kernel locks (used to ensure that multiple processes don't write to a file at the same time) |
| /proc/meminfo | Information about physical memory and swap-space usage |
| /proc/misc | Miscellaneous information |
| /proc/modules | List of loaded driver modules |
| /proc/mounts | List of mounted file systems |
| /proc/net | Directory with many subdirectories that contain information about networking |
| /proc/partitions | List of partitions known to the Linux kernel |
| /proc/pci | Information about PCI devices found on the system |
| /proc/scsi | Directory with information about SCSI devices found on the system (present only if you have SCSI device) |
| /proc/stat | Overall statistics about the system |
| /proc/swaps | Information about the swap space and how much is used |
| /proc/sys | Directory with information about the system. You can change kernel parameters by writing to files in this directory. (Using this method to tune system performance requires expertise to do property) |
| /proc/uptime | Information about how long the system has been up |
| /proc/version | Kernel version number |

## Persistent naming udev

* sysfs: displays all the devices in the system as well as lots of information about each device, including the location of the device on the bus, attributes such as name and serial number, and the major and minor numbers of the device.
* /sbin/hotplug: Program called whenever a device is added or removed and can do whatever is necessary to handle the device.
* /sbin/udev: Dynamically named devices based on device characteristics such as serial number, device number on a bus
* /etc/udev/udev.conf: Creates device nodes automatically in the directory specified

## Manging Users

* /etc/default/useradd: Specified the default shell (/bin/bash) and the default home directory location (/home)
* /etc/login.defs: Provides system wide defaults for automatic group and user IDs, as well as password-expiration parameters
* /etc/skel: A directory that contains the default files that useradd creates in the user's home directory

## Log configuration directory

* /etc/syslog.conf: man syslog.conf
* /etc/rsyslog.conf: man rsyslog.conf

## usr directory hierarchy

| Directory | Secondary Directory Hierarchy |
| --- | --- |
| /usr/bin | Most user commands |
| /usr/games | Many games install here though they are not technically required to do so other than for historic reasons |
| /usr/include | Directory for include files -- files that are inserted into source code of applications by using various directives -- used in developing Linux applications |
| /usr/lib | Libraries used by software packages and for programming |
| /usr/libexec | Libraries for applications |
| /usr/local | Any local software |
| /usr/sbin | Nonessential system administrator utilities |
| /usr/share | Shared data that doesn't depend on the system architecture (whether the system is an Intel PC or a Sun SPARC workstation) |
| /usr/src | Source code |

## var directory hierarchy

| Directory | Variable Data |
| --- | --- |
| /var/cache | Cached data for applications |
| /var/crash | Dump files from kernel crashes |
| /var/lib | Information relating to the current state of applicatins |
| /var/lock | Lock files to ensure that a resource is used by one application only |
| /var/log | Log files organized into subdirectories |
| /var/mail | User mailbox files |
| /var/opt | Variable data for packages stored in the /opt directory |
| /var/run | Data describing the system since it was booted |
| /var/spool | Data that's waiting for some kind of processing |
| /var/tmp | Temporary files preserved between system reboots |
| /var/yp | Network information Service (NIS) database files |

## NFS Installation

```
sudo apt install nfs-kernel-server
systemctl status nfs-kernel-server
systemctl enable nfs-server
systemctl start nfs-server
sudo firewall-cmd --add-service={nfs,nfs3,mountd,rpc-bind} --permanent
sudo firewall-cmd --reload

```

* Add to /etc/exports file

```
/share textbox(rw)
/share 192.168.1.200(rw)

```

```
exportfs -a
systemctl restart nfs-server

```

### Mount NFS

```
mkdir /mnt/myserver
mount myserver:/share /mnt/myserver

```

### Mount DOS Partition

```
mount -t vfat /dev/hda1 /dosc

```

### Mount NTFS Partition

```
mount /dev/sda2 /mnt/windir -t ntfs
mount /dev/sda2 /mnt/windir -t ntfs -r -o umask=0222

```