# Linux boot methods

## SysVinit Method

* /etc/inittab: File that specifies which processes to start at different runlevels.
* /etc/init.d: Directory and subdirectors (begin with rc)

### Runlevels in Linux

| Runlevel | Meaning |
| --- | --- |
| 0 | Shut down the system |
| 1 | Runs in single-user stand-alone mode (No one else can log in; you work at the text console) |
| 2 | Runs in multiuser mode (Debian and Ubuntu use runlevel 2 as the default runlevel) |
| 3 | Runs in full multiuser mode (for text-mode login in Fedora and SUSE) |
| 4 | Run in full multiuser mode (unused in Fedora and SUSE) |
| 5 | Run in full multiuser mode (the default runlevel with graphical login in Fedora and SUSE) |
| 6 | Reboot the system |

#### Current run level

```
/sbin/runlevel

```

#### Fields in inittab entry

| Field | Meaning |
| --- | --- |
| id | A unique one-or two-character. The init process uses this field internally. You can use any identifier you want as long as you don't use the same identifier on more than one line |
| runlevels | A sequence of zero or more characters, each denoting a runlevel. For example, if the runlevel is 12345, that entry applies to each of the runlevels (1 through 5). This field is ignored if the action field is set to sysinit, boot, or bootwait |
| action | What the init process will do with this entry. If this field is initdefault, for example, init itnerprets the runlevels field as the default runlevel. If this field is set to wait, init starts the program or script specified in the process field and waits until that process exists |
| process | Name of the script or program that init starts. Some settings of the action field require no process field. When the action field is initdefault, for example, there's no need for a process field |

#### Automatically starting services

```
chkconfig --level 345 sshd on

chkconfig --list

```

## Systemd Method

* /usr/lib/systemd/system: Folder thar stores unit configuration files

### Systemctl Commands

| Command name | Explanation |
| --- | --- |
| get-default | Displays the default target configured for the system |
| list-units | Displays the current status of all configured units |
| default name | Changes to the default target unit |
| isolate name | Starts the named unit and stops all others |
| start name | Starts the named unit |
| stop name | Stop the named unit |
| reload name | Causes the named unit to reload its configruation file |
| restart name | Causes the named unit to shut down and restart |
| status name | Displays the status of the named unit (You can pass a PID value rather than a name, if you like) |
| enable name | Cofigures the unit to start when the computer next boots |
| disable name | Confiures the unit to not start when the computer next boots |
