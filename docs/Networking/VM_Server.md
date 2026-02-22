# VM Server

* Built with proxmox
* Connected with an internal NAT that can't be accessed from the outside, but can access the internet
* Internal NAT handled by raspberry pi
* dhcp server handled by raspberry pi to give ips within the network 192.168.2.1/24

## Rasperry pi Server

* /etc/dhcpcd.conf

```
interface eth0
static ip_address=192.168.2.1/24
#static routers=102.168.2.1
metric = 200

```

* iptables adding NAT routing for rasberrypi [github script here](https://github.com/garfield8123/nat_raspberrypi)

## VM Templates

* Uses Qemu-guest additions, rc.0 script files custom build to change machine id on shutdown
* Uses machine id reset on proxmox for ubuntu to DHCP properly templates

```
# Clear machine-id
if [ -f /etc/machine-id ]; then
    cat /dev/null > /etc/machine-id
fi

if [ -f /var/lib/dbus/machine-id ]; then
    rm -f /var/lib/dbus/machine-id
fi

# Linking /var/lib/dbus/machine-id to /etc/machine-id means it will not
# need to be regenerated later and it will always be the same.
ln -s /etc/machine-id /var/lib/dbus/machine-id
exit 0

```

## Windows 10 VM Machine

* Passthrough of Physical GPU to Windows VM
* Uses RDP to connect to machine
* Uses Moonlight to stream videogame/display content
* Device Manager showing Windows showing Physical GTX 950 graphics card

```
Memory Address 0x80000000-0x810FFFFF    PCI-to-PCI Bridge
Memory Address 0x80000000-0x810FFFFF    NVIDIA GeForce GTX 950
Memory Address 0x80000000-0x810FFFFF    PCI Express Root Complex

```

## Resize VM Size

```
sudo pvscan
sudo lvextend --size +10G --resizefs /dev/<vg-name>/<lg-name>

```

## MDM server

Fleet MDM server

```
# Running preview
./fleetctl preview

192.168.2.218:1337

username: [email protected]
Passsword: preview1337#

```

Add hosts

Install [Node JS](https://nodejs.org/en/download)

```
sudo npm install -g fleetctl
sudo fleetctl package --type=deb --enable-scripts --fleet-desktop --fleet-url= --enroll-secret=3lQo50AT90LbXsrYZaqZ601OircZUatQ

sudo dpkg -i fleet*.deb

```