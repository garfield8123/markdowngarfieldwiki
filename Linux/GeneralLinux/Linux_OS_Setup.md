# Linux OS Setup

Setup process for OS

* [Linux OS Setup](#linux-os-setup)
* [Centos](#centos)
  + [Centos GUI](#centos-gui)
* [Ubuntu](#ubuntu)
  + [Ubuntu Update](#ubuntu-update)
* [OpenSuse](#opensuse)
  + [OpenSuse Update](#opensuse-update)
* [Fedora](#fedora)
  + [Fedora Update](#fedora-update)

## Centos

### Centos GUI

Install Centos GUI, change to run level target

```
sudo yum groupinstall "GNOME Desktop" "Graphical Administration Tools"
sudo ln -sf /lib/systemd/system/runlevel5.target > /etc/systemd/system/default.target
sudo reboot

```

## Ubuntu

### Ubuntu Update

Update Ubuntu, release upgrade, distribution upgrade

```
sudo apt-get update
sudo apt-get dist-upgrade
sudo do-release-upgrade

```

## OpenSuse

### OpenSuse Update

zypper update opensuse

```
sudo zypper patch

```

## Fedora

### Fedora Update

fedora upgrade

```
dnf upgrade

```