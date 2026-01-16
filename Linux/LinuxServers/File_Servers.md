# File Servers

* Different Fileservers
* [Network File Share (NFS)](#network-file-share-nfs)
* [Samba (SMB)](#samba)

## Network File Share (NFS)

nfs-utils provides both the drivers to support NFS and the client and server to share folders.

* /etc/exports: Export one or more directories exportfs

### Installing NFS

```
sudo apt install nfs-kernel-server
systemctl status nfs-kernel-server

yum install nfs-utils
sudo systemctl enable nfs-server
sudo systemctl start nfs-server

sudo firewall-cmd --add-service={nfs,nfs3,mountd,rpc-bind} --permanent
sudo firewall-cmd --reload

```

### Exports file

```
/share textbox(rw,sync)

/share 192.168.0.0/24(rw,sync)
Directory host1(options) host2(options)

```

exportfs -a

### Exports Options

| Option | Description |
| --- | --- |
| General Options |  |
| secure | Allows connections only from port 1024 or lower (default) |
| insecure | Allows connections from port 1024 or higher |
| ro | Allows read-only access (default) |
| rw | Allows both read and write access |
| sync | Performs write operations (writing information to the disk) when requested (by default) |
| async | Performs write operatios when the server is ready |
| no\_wdelay | Performs write operations immediately |
| wdelay | Waits a bit to see whether related write requests arrive and then performs them together (by default) |
| hide | Hides an exported directory thats a subdirectory of another exported directory (by default) |
| no\_hide | Causes a directory to not e hidden (opposite of hide) |
| subtree\_check | Performs subtree checking, which involves checking parent directories of an exported subdirectory whenever a file is accessed (by default) |
| no\_subtree\_check | Turns off subtree checking (Opposite of subtree\_check) |
| insecure\_locks | Allows insecure file locking |
| User ID Mapping Options |  |
| all\_squash | Maps all user IDs and group IDS to the anonymous user on the client |
| no\_all\_squash | Maps remote user and group IDs to similar IDs on the client (by default) |
| root\_squash | Maps remote root user to the anonymous user on the client (by default) |
| no\_root\_squash | Maps remote root user to the local root user |
| anonuid=UID | Sets the user ID of anonymous user to be used for the all\_squash and root\_squash options |
| anongid=GID | Sets the group ID of anonymous user to be used for the all\_squash and root\_squash options |

### Moutning NFS

```
mkdi /mnt/myserver
mount myserver:/share /mnt/myserver
mount
myserver:/share on /mnt/myserver type nfs (rw,addr=192.168.0.4)

```

## Samba

Windows is the System Message Block (SMB). Samba software package to allow Linux to interact with Window clients and servers

### Samba Components

| Package | Description |
| --- | --- |
| /etc/samba/smb.conf | The samba configuration file that the server message block server uses |
| /etc/samba/smbusers | Samba configuration file showing usernames that correspond to usernames on the pc |
| nmbd | NetBIOS name server, which clients use to look up servers |
| nmblookup | Command that returns IP address of windows PC identified by NetBIOS name |
| smbadduser | A program that adds users to the SMB password file |
| smbcacls | Program that manipulates Windows NT access control lists on shared files |
| smbclient | Windows client, which runs on Linux and allows linux to access files and printer on windows server |
| smbcontrol | A program that sends messages to the smd, nmbd, or winbindd process |
| smbd | SMB server, which accepts connections from Windows clients and provides file-sharing and print-sharing services |
| smbmount | A program that mounts a samba share directory on a linux pc |
| smbpasswd | A program that changes the password for an SMB user |
| smbprint | A script that enables printing on a printer on the SMB server |
| smbstatus | A command that lists the current SMB connections for the local host |
| smbtar | A program that backs up SMB shares directory to tape drives on the Linux system |
| smbumount | A program that unmounts a currently mounted samba share directory |
| testparm | A program that ensures that the samba configruation file is correct |
| winbindd | Server that resolves names from Windows NT servers |


### Install Samba Fedora
```shell
dnf install samba samba-common samba-client s
sudo systemctl enable smb --now
sudo systemctl enable nmb --now
sudo systemctl restart smb nmb
firewall-cmd --get-active-zones
sudo firewall-cmd --permanent --zone=FedoraWorkstation --add-service=samba
sudo firewall-cmd --reload
```

### Create samba user
```shell
sudo smbpasswd -a garfield
```

### change enforcing policy
```shell
sudo semanage fcontext -a -t samba_share_t "/smbfolder(/.*)?"
sudo restorecon -Rv /smbfolder
```

### smb.conf
```text
[smbfolder]
	path = /smbfolder
	browseable = yes
	writeable = yes
	valid users = @smbgroup
	force group = smbgroup
	create mask = 0664
	directory mask = 2775
```

### Samba firewall
```shell
sudo firewall-cmd --add-port=445/tcp --permanent
sudo firewall-cmd --reload
```

### Create users and groups
```shell
groupadd smbgroup
usermod -g smbgroup garfield
```


### Installing Samba Other OS

```
sudo apt-get install samba

sudo dnf install samba

sudo systemctl enable smb
sudo systemctl start smb

sudo firewall-cmd --add-service=samba --permanent
sudo firewall-cmd --reload

```

### Configuring Samba

* /etc/samba/smb.conf

```
[sambashare]
 comment = "My WIndows share on rocky"
 path=/share
 read only = no
 browsable = yes

```

```
testparm
sudo smbpasswd -a rich

```

## Peer-to-peer

One workstation enables another workstation to access files stored locally on its hard drive

## Client-server

Utilizes a centralized file server for sharing files that multiple clients can access and modify as needed