# Active Directory

Use Active Directory with Windows Server 2022

## Windows Server Installation

### Installation Instructions

```
Install-WindowsFeature -name AD-Domain-Services -IncludeManagementTools
Get-Help Add-ADDSReadOnlyDomainControllerAccount
Invoke-Command { Install-ADDSDomainController -DomainName garfield8123.com -Credential (Get-Crdential) } - ComputerName garfield

```

GUI

* Server Manager -> Manage -> Add Roles and Features

### User Creation

![active directory windows](../../images/activedirectorywindows.png)

* Created an additional user in window server
* Created a user garfield within the windows server 2022 active directory

GUI

* Server Manager -> Tools -> Active Directory Users and Computers

## Adding Active Directory to Proxmox

![Proxmox realm](../../images/realmproxmox.png)

* Datacenter -> Realm -> Add -> Active Directory Server
* Fill out realm title, Domain (garfield8123.com), srever (192.168.2.110)
* Sync Options -> Bind user (garfield) -> Bind password (Password for garfield)

## Adding Active Directory to Linux

![Linux realm](../../images/RealmLinux.png)

### Prerequiste installation

```
sudo yum install sssd realmd oddjob oddjob-mkhomedir adcli samba-common samba-common-tools krb5-workstation openldap-clients policycoreutils-python -y

```

### Join Realm

```
sudo realm join --user=Administrator 192.168.2.110
sudo realm list

```