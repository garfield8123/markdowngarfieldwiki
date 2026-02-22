# Ports & Protocols

* Located in /etc/services
* [Logging types](#logging)
* [Certficate Authorities](#certificate-authorities-ca)

## Well Known Ports

| Port | Protocol | Info |
| --- | --- | --- |
| 20 & 21 | FTP | [More Info](#file-transfer-protocol-ftp) |
| 22 | SSH | [More Info](#secure-socket-shell-ssh) |
| 23 | Telnet | [More Info](#telnet) |
| 25 | SMTP | [More Info](./mailservers.md) |
| 53 | DNS | [More Info](#domain-name-service-dns) |
| 67 | DHCP | [More Info](#dynamic-host-configuration-protocol-dhcp) |
| 69 | TFTP | [More Info](#trivial-file-transfer-protocool-tftp) |
| 80 | HTTP | [More Info](./webservers.md) |
| 88 | Kerberos | [More Info](#kerberos) |
| 109 & 110 | POP | [More Info](./mailservers.md) |
| 119 | NNTP | [More Info](#network-news-transfer-protocol-nntp) |
| 123 | NTP | [More Info](#network-time-protocol-ntp) |
| 137 - 139 | SMB | [More Info](#samba) |
| 143 & 220 | IMAP | [More Info](./mailservers.md) |
| 161 & 162 | SNMP | [More Info](#simple-network-management-protocol-snmp) |
| 389 | LDAP | [More Info](#lightweight-directory-access-protocol-ldap) |
| 443 | HTTPS | [More Info](./webservers.md) |
| 465 | Rendezvous DIrectory Service Cisco | unknown |
| 514 | NIS | [More Info](#network-information-system-nis) |
| 631 | IPP | [More Info](#common-unix-printing-system-cups) |
| 993 | IMAP SSL/TLS | [More Info](./mailservers.md) |
| 995 | POP SSL/TLS | [More Info](./mailservers.md) |
| 3306 | MYSQL | [More Info](./database.md) |
| 2049 or 111 | NFS | [More Info](#network-file-share-nfs) |

## Common Unix Printing System (CUPS)

CUPS uses Internet Printing Protocol (IPP) allows you to share local prints with other linux systems and share among users

## Network File Share (NFS)

nfs-utils provides both the drivers to support NFS and the client and server to share folders.

## Samba

Windows is the System Message Block (SMB). Samba software package to allow Linux to interact with Window clients and servers. NetBIOS windows networking and uses several ports for the session

## Dynamic Host Configuration Protocol (DHCP)

Most popular DHCP server package is called DHCPd (Internet Systems Consortium (ISC)). Packages: dhclient, dhcpd, pump

## Logging

Two main logging systems. rsyslogd (accepts logging data from remote servers) used by SysVinit and Upstart systems. jurnald (systemd system for local and remote logging of system information)

## Domain Name Service (DNS)

Linux servers use BIND software package to provide DNS naming services

## Simple Network Management Protocol (SNMP)

A way for admins to query remote network devices and servers to obtain information about their config, status, and even performance.
SNMPv1: Only simple password authentication of clients and passed data as plain text
SNMPv2: basic security and provided bulk transmission of monitoring data
SNMPv3: utilizes both strong authentication and data encryption capabilities as well as more streamlined management system
net-snmp package: securely monitor aspects of Linux server remotely

## Network Time Protocol (NTP)

ntpd program synchronizes a Linux system with remote systems. synchronize with remote time standard server

## Network Information System (NIS)

NIS directory service that allows both clients and servers to share common naming name directory. NIS+ same, but more security
nis-utils open source for implementing NIS+ directory

## Kerberos

Secure authentication protocol, securely authenticate users with a centralized server database

## Lightweight Directory Access Protocol (LDAP)

Created to provide simple network authentication services to multiple applications and devices on a local network
OpenLDAP: Hierachal database to store objects in network
The Lightweight Directory Access Protocol (LDAP) provides access to directory services for authenticating users, workstations, and other network devices

## Certificate Authorities (CA)

OpenSSL provides standard certificate functions for server & clients

## Secure Socket Shell (SSH)

Provides a layer for remote login and other secure network services over an insecure network

## Network News Transfer Protocol (NNTP)

Distribution of news articles in a store-and-forward fashion across the internet

## Telnet

Used when a user on one system logs in to another system on the internet. (The user must provide a valid user ID and password to log in to the remote system)

## File Transfer Protocol (FTP)

Used to transfer files between computers on the internet.

## Trivial File Transfer Protocool (TFTP)

Transferring files from one system to another (Typically used by X terminals and diskless workstations to download boot files from another)