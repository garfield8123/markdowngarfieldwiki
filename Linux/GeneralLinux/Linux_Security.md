# Linux security

## Security Framework

![security framework](/images/securityframework.jpg)

## Determining business requirements

Identify the computer resources and information that you have to protect (Including any requirements imposed by laws, requirement to protect the privacy of some types of data)

* Enabling access to information by authorized users
* Implementing business rules that specify who has access to what information
* Employing a strong user-authentication system
* Denying execution to malicious or destructive actions on data
* protecting data from end to end as it moves across networks
* Implemnting all security and privacy requiremtns that laws impose

## Risk analysis

* Threats -> What you're protecting against
* Vulnerabilites -> Weaknesses that may be exploited by threats (the risks)
* Probability -> The likelihood that a threat will exploit the vulnerability |
* Impact -> The effect of exploiting a specific vulnerability
* Mitigation -> What to do to reduce vulnerabilities

### 123 of risk analysis

1. Assign subjective ratings of low, medium, and high to the probability
2. Assign similar ratings to the effect
3. Assign a numeric value to the three levels -- low=1, medium=2, and high=3 --for both probability and effect
4. Multiple the probability by the effect
5. Decide to develop protections for vulnerabilities that exceed a specific threshold for the product of probability and effect

## Common Security terminaology

| Term | Description |
| --- | --- |
| Application gateway | A proxy service that acts as a gateway for application-level protocols, such as FTP, HTTP, NNTP, and ssh |
| Authentication | Process of confirming that a user is indeed who they claim to be. The typical authentication method is a challenge-response method wherein the user enters a username and secret password to confirm their identity |
| Backdoor | A security weakness that a cracker places on a host to bypass security firewalls |
| Bastion host | A highly secured computer that serves as an organization main porint of presence on the internet. A bastion host typically resides on the perimeter network, but a dual-homed hosted (with one network itnerface connected to the internet and the other to the internal network) is also called a bastion host |
| Buffer overeflow | A security flaw in a progra that enables a cracker to send an excessive amount of data to that program and to overwrite parts of the running gprogram iwth code in the data being sent. The result is that the cracker can execute arbitrary code on the systemand possibly gain access to the system as a privlleged user. The exec-shield feature of the linux kernel protects against buffer overflows |
| Certificate | Electronic document that identifies an entity (such as person, an organization, or a cocmputer) and associates a public key with that identity. A certificate contains the certificate holder's name, a serial number, an expiration date, a copy of the certificate holder's public key, and the digital signature of the certificate authority so that a receipent can verify that the certificate is real |
| Certificate authority (CA) | An organization that validates identifies and issues certificates |
| Cracker | A person who breaks into (or attempts to break into) a host, often with malicious intent |
| DDOS | A variant of DOS that uses a coordinated attack from a distributed system of computers rather than a single source. Often uses worms to spread to -- and take control of -- multiple computers that can then attack the target |
| Decryption | The process of transforming encrypted information into its original, intelligible form |
| Digital signature | A one way MD5 (Message Digest algorithm 5) or SHA-1 (Secure Hash Algorithm -1) hash of a message encrypted with the private key of the message originator, used to verify the integrity of a message and ensure nonrepudiation |
| DMZ | Aother name for the perimeter network |
| DoS | Attack that uses so many of the resources on your computer and network that legitmate users can't access and use the system. From a single source, the attack overwhelms the target computer with messages and blocks legitimate traffic. |
| Dual-homes host | A computer with two network interfaces |
| Encryption | The process of transforming information so that it's unintelligible to anyone but the intended recipient. Transformation is performed by a mathematical operation between a key and the information |
| Exploit tools | Publicly available and sophisticated tools that intruders of various skill levels can use to determine vulnerabilities and gain entry into targeted systems |
| Firewall | A controlled-acess gateway between an organization's internal network and the internet. A dual-homed host can be configured as a firewall |
| Hash | The result when a mathematical function converts a message to a fixed-size numberic value known as a message edigest (or hash). The MD5 algorithm, for example, produces a 128 bit message digest. SHA 1 generates a 160 bit message digest. The hash of a message is encrypted with the private key of the sender to produce the digital signature |
| Host | A computer on a network that's configured to offer services to other computers on the network |
| Integrity | For received data, a state of being the same as originally sent (that is unaltered in transit) |
| IP Spoofing | An attack in which a cracker figures out the IP address of a trusted host and then sends packets that appear to come from the trusted host. The attacker can send packets but can't see responses. But the attacker can predict the sequence of packets and essentially send commands that set up a backdoor for future break-ins |
| IPSec (IP Security protocol) | Security protocol for the network layer of the OSI networking model, designed to provide cryptographic security services for IP packets. IPSec provides encryption based authentication, integrity, access control, and confidentialitiy |
| Logic bomb | Form of sabotage in which programmer inserts code that causes the program to perform a destructive action when some triggering event occurs, such as terminating the programmer's employment |
| Nonrepudiation | Security feature that prevents the sender of data from being able to deny having sent the data |
| packet | A collection of bytes, assembled accoridng to a specific protocol, that serves as the basic unit of communication on a network. On TCP/IP networks, for example, the packet may be referred to as an IP packet or a TCP/IP packet |
| packet filtering | Selective blocking of packets according to type of packet (as specified by the source and destination IP address or port) |
| Perimeter network | Netowrk between the internet and the protected internal network. The perimeter network (DMZ) where the bastion host resides |
| Port Scanning | Method of discovering which ports are open on a system, performed by sending connection requests to the ports. Procedure is usally a precursor to further attacks (nmap and netstat) |
| proxy server | Server on the bastion host that enables internal clients to access external servers (enables external clients to access servers inside the protected network). |
| Public Key Cryptography | An encryption method that uses a pair of keys -- a private key and a public key -- to encrypt and decrypt the information. Anything encrypted with the public key can be decrypted only with the corresponding private key |
| Public Key Infrastructure (PKI) | A set of standards and services that enables the use of public key cryotography and certificates in a networked environment, PKI facilities tasks such as issuing, renewing, and revoking certificates, and generating and distributing public and private key pairs |
| Screening router | Internet router that filters packets |
| Setuid Program | Setuid or suid runs with the permissions of the pgogram owner, regardless of who actually runs it. If root owns a setuid/suid program that program has root privileges regardless of who started the program. Crackers often exploit vulnerabilites in setuid programs to gain privileged access to a system. se group id (sgid) same issue |
| Sniffer | packet sniffer -- a program that intercepts routed data and exmamines each packet in search of specified information such as passwords transmitted in clear text |
| Spyware | Software that covertly gathers user information through the user's internet connection and usually transmits that information in the background to someone else. Spyware can also gather information about email addresses and even passwords and credit card numbers. Spyware is similar to a Trojan horse in that users are tricked into isntalling spyware when they install something else |
| Symmetric key encryption | An encryption method wherein the same key is used to encrypt and decrypt the information |
| Threat | An event or activity, delierate or unintentional, with the potential for causing harm to a systemme or network |
| Trojan horse | A program that masquerades a sbenign program, but is really backdoor used for attacking a system. Attacks often install a collection of Trojan horse programs that enable the attacker to freely access the system with root privileges yet hide that fact from the system administrator. Such collections of Trojan horse programs are called rootkits |
| virus | Self replicating program that spreads from one computer to another by attaching itself to other programs |
| vulnerability | A flaw or weakness that may cause harm to a system or network |
| War-dialing | Using simple programs that dial consecutive phone numbers looking for modems |
| War-driving | A method of gaining entry into wireless computer networks that uses a computer, antennas, and a wireless network card and that involves patrolling locations to gain unauthorized access |
| worm | A self-replicating program that copies itself from one computer to another over a network |

## Common Security Tools

| Tool | Description |
| --- | --- |
| chage | Modify the time between required password chanes (both min, max number of days), the number of days of warning to be given that a change must be made |
| find | Allows you to find anathing on the machine |
| lsof | list open files |
| netstat | Status of the networkr, including network connections, routing tales and statistics per interface. Similiar command SS |
| nmap | Used to scan the network and create a map of what's avilable on it |
| passwd | Utility with which users can change their passwords at their command line whenever necessary |
| su | Become another user, can be used within the current user's session. |
| sudo | Perform a job with elevated privileges, sudo enables the user to just run that task with elevated privileges |
| ulimit | Resource limits on shells can be set or viewed using this command to keep one user from hogging all resources |
| usermod | enhanced version of change. Can be used to set/change password expiration parameters and to specify a default shell, lock or unlock an account |

## Changing user security

```
chage -l root
chage -M 90 root # maximum days

```

## Adding users

```
useradd -c "Rich Blum" rblum
passwd rblum
userdel rblum
userdel -r rblum

```

* /etc/default/useradd: Specified the default shell (/bin/bash) and the default home directory location (/home)
* /etc/login.defs: Provides system wide defaults for automatic group and user IDs, as well as password-expiration parameters
* /etc/skel: A directory that contains the default files that useradd creates in the user's home directory
* usermod -g root rblum: root as primary group
* groupadd {name}: Creates a new group automatically

## Fields in /etc/group file

| Field Name | Meaning |
| --- | --- |
| groupname | The name of the group (such as wheel) |
| password | The group password (An x means that the password is stored in the /etc/shadow file) |
| GID | The numerical group ID (such as 10) |
| membership | A comma-separated list of usernames that belong to this group (such as root,rblum) |

## File/Folder Permissions code

| who | action | permission |
| u (user) | + (add) | r (read) |
| g (group) | - (remove) | w (write) |
| o (others) | = (assign) | x (execute) |
| a (all) | s (set user ID) | |

```
chmod a+x file

```

## find SUID programs

```
find / -type f -perm /4000

```

## gpg keys

```
gpg --gen-key

gpg --list-keys

gpg --armor --export [email protected] > richkey.asc

gpg --import richkey.asc

gpg --fingerprint [email protected]

gpg --sign-key [email protected]

```

### Signing file

```
gpg -i message.sig -s message
gpg --verify message.sig

gpg -i message --decrypt message.sig
gpg -i message.asc --clearsign message

gpg --verify message.asc

```

### Encryping and decrypting

```
gpg -o message.gpg -e -r [email protected] message

gpg -o message --decrypt message.gpg

gpg -o secret.gpg -c somefile # encrypt file

gpg -o myfile --decrypt secret.gpg # decrypt

```

## OpenSSH security

| Component | Description |
| --- | --- |
| /usr/sbin/sshd | The ssh daemon must run ona host if you want users on a remove systems to use the ssh client to log in securely. When a connection from the ssh client arrives sshd performs authentication by using public key cryotpgraphy and establishes an encrypted communication link with the ssh client |
| /usr/bin/ssh | Users cna run this ssh client to log in to a host running sshd. |
| /usr/bin/slogin | Component is a symbolic link to /usr/bin/ssh |
| /usr/bin/scp | Secure copy program works like rcp, but secure. Uses SSH for data transfer and provides the same authentication and security as ssh |
| /usr/bin/ssh-keygen | Generate the public and private key pairs that you need for public key cryotogrpahy in Openssh. generate key pairs for both RSA and DSA (Digital signature algorithm). |
| /etc/ssh/sshd\_config | Configuration file for the sshd server specifies many parameters for sshd, including the port to listen to, the protcol to use, and the location of other files |
| /etc/sshd/ssh\_config | Configuration file for the ssh client, each user can have an ssh configuration file named config in the .ssh subdirectory of the user's home directory |

## Security files to be aware

| File | Description |
| --- | --- |
| /etc/nologin | If this file exists, denies login to all users except root. File can be handy when maintenace needs to be done and users need to stay off the system for a period of time. Removing the file restores login capability for all users. The file can be created as a text file with any editor, or you can often use the nologin command to create it |
| /etc/passwd | Holds much of the user account information |
| /etc/shadow | When shadowing is turned on -- which it almost always is -- password vlaues (hashes) are stored in this file (which is more secure) as opposed to in /etc/passwd |
| /etc/xinetd.d/\* | Directory can be used to store configuration files used by xinetd, the server daemon |
| /etc/xinetd.conf | This file is the main configuration file used by xinetd, the server daemon |
| /etc/inetd.d/\* | Directory can be used to store configuration files used by inetd, the internet daemon in almost all distributions inetd has been replaced by xinetd |
| /etc/inetd.conf | This file is the main configuration file used by inetd, the internet daemon |
| /etc/inittab | This file is the initial startup (initialization) table used to identify what starts and stps as the system is booted and changes run states |
| /etc/init.d/\* | The directory can hold configuration files that are used during the change of run states level and referenced by inittab file |
| /etc/hosts.allow | If this file exists, it specifcaly lists the hosts that are allowed to network with this one, if the file doesn't exist, by default all hosts are allowed to network with this one |
| /etc/hosts.deny | If this file exists, it specifically lists the hosts that aren't allowed to network with this one. Having an allow file that identifies only hosts that can network with this one; having a deny file that identifies only hosts that can't connect with this one; having neither file, allows all other hosts to network with this one |

## Security Audits

* independent verification=organization comlies with its existing policies and procedures for computer security (nontechnical aspect)
* Independent testing=technical aspect

### Nontechnical aspect

* documents, interviewing people

### Technical aspect

* how well host and network is secured.

## Computer vulnerabilites

* SANS institue newsletters
* CVE
* National Vulnerability database (nvd.nist.org)

| vulnerability type | Description |
| --- | --- |
| BIND DNS | Berkeley Internet Domain Name (BIND) package that implements the Domain Name System (DNS), the internet's name service that translates a name to an IP address |
| Apache Web Server | Some Apache modules (mod\_ssl) have known vulnerabilities. Any vulnerability in Common Gateway Interface (CGI) programs used with web servers to process interactive web pages can give attackers a way to gain access to a systme |
| Authentication | User accounts sometimes have no passwords or have weak passwords that are easily cracked by password-cracking programs |
| CVS,Subversion | Concurrent Versions Systems (CVS) popular source code control system in Linux systems. Subversion is another version control system. These version control systems have vulnerabilites that can enable an attacker to execute arbitrary code |
| sendmail | Complex program used to transport mail messages from one system to another. |
| SNMP | Simple Network Management Protocl (SNMP) used to remotely monitor and administer various network connected systems ranging from routers to computers. SNMP lacks good access control, so an attacker may be able to reconfigure or shut down your system running SNMP |
| Open Secure Sockets Layer (Open SSL) | Many applications such as Apache Web Server use OpenSSL to provide crytogrpahic security for network connection. |
| Network File System (NFS) and Network Information Service (NIS) | Both NFS and NIS have many security problems (buffer overflow, potential for denial-of-service attacks, and weak authentication). NFS and NIS are often misconfigured, which could allow local and remote users to exploit the security holes |
| Databases | Databases like MySQL and PostgreSQL are complex applications that can be difficult to configure and secure correctly. These databases have many features that can be misused or exploited to compromise the confidentiality, availability, and integrity of data |
| Linux Kernel | The Linux kernel is susceptible to many vulnerabilites, such as denial of service, execution of aritrary code, and root level access to the system |

## File Permissions

| File Path | Permission | Description |
| --- | --- | --- |
| /boot/grub/menu.lst | 600 | GRUB bootloader menu file |
| /etc/cron.allow | 400 | List of users permitted to use cron to submit periodic jobs |
| /etc/cron.deny | 400 | List of users who can't use cron to submit periodic jobs |
| /etc/crontab | 644 | Systemwide periodic jobs |
| /etc/hosts.allow | 644 | List of hosts allowed to use internet services that are started with TCP wrappers |
| /etc/hosts.deny | 644 | List of hosts denied access to internet services that are started with TCP wrappers |
| /etc/logrotate.conf | 644 | File that controls how log files rotate |
| /etc/pam.d | 755 | Directory with configuration files for pluggable authentication modules (PAMs) |
| /etc/passwd | 644 | Old style password file with user account information ut not the passwords |
| /etc/rc.d | 755 | Directory with system-startup scripts |
| /etc/securetty | 600 | TTY interfaces (terminals) from which root can log in |
| /etc/security | 755 | Policy files that control system access |
| /etc/shadow | 400 | File with encrypted passwords and password expiration information |
| /etc/shutdown.allow | 400 | Users who can shut down or reboot by pressing Ctrl+Alt+Delete |
| /etc/ssh | 755 | Directory with configuration files for SSH |
| /etc/sysconfig | 755 | System configuration files |
| /etc/sysctl.conf | 644 | Kernel configuration parameters |
| /etc/syslog.conf | 644 | Configuration file for the syslogd server that logs messages |
| /etc/udev/udev.conf | 644 | Configuration fiel for udev -- the program that provides the capability to dynamically name hot-pluggable devices and create the device files in the /dev directory |
| /etc/vsftpd | 600 | Configuration file for the Very Secure FTP server |
| /etc/vsftpd.ftpusers | 600 | List of users who aren't allowed to use FTP to transfer files |
| /etc/xinetd.conf | 644 | Configuration file for the xinetd server |
| /etc/xinetd.d | 755 | Directory containing configuration files for specific services that the xinetd server can start |
| /var/log | 755 | Directory with all log files |
| /var/log/lastlog | 644 | Information about all previous logins |
| /var/log/messages | 644 | Main system message log file |
| /var/log/wtmp | 664 | Infformation about current logins |

## Password security

| File pathname | Ownership | Permission |
| --- | --- | --- |
| /etc/group | root.root | 644 |
| /etc/passwd | root.root | 644 |
| /etc/shadow | root.root | 400 |

## Security Testing Tools

| Type | name of tools |
| --- | --- |
| Port scanners | nmap, strobe |
| Vulnerability scanners | Nessus Security Scanner, SAINT, SARA, Whisker (CGI scanner), ISS Internet Scanner, CyberCop Scanner, Vetescan, Retina Network Security Scanner |
| Network utilities | Netcat, hping2, Friewalk, Cheops, ntop, ping, ngrep, AirSnort(802.11 WEP encryption-cracking tool) |
| Host-Security Tools | Tripwire, lsof |
| Packet sniffers | tcpdump, ethereal, dsniff, sniffit |
| Intrusion Detection | Aide (advanced Intrusion Detection Environment), Snort, Aabacus Portsentry, scanlogd, NFR, LIDSSystems (IDSs) |
| Log Analyssis and Monitoring tools | logcolorise, tcpdstats, nlog, logcheck, logwatch, swatch |
| Password cracking tool | John the ripper |
