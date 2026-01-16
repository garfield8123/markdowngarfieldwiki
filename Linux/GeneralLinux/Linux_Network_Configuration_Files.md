# Linux Network Configuration Files

| Distribution | Network Configuration Location |
| --- | --- |
| Debian based | /etc/network/interfaces file |
| Red Hat based | /etc/sysconfig/network-scripts directory |
| openSUSE | /etc/sysconfig/network file |

## Debian Based

```
auto eth0
iface eth0 inet static
    address 192.168.1.77
    netmask 255.255.255.0
    gateway 192.168.1.254
iface eth0 inet6 static
    address 2003:aef0::23d1::0a10:00a1
    netmask 64
    gateway 2003:aef0:;23d1::0a10:0001

auto eth0
iface eth0 inet dhcp
iface eth0 inet6 dhcp

```

## Red Hat Based

File ifcfg-interface (ifcfg-enp0s3)

```
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
OOTPROTO=dhcp
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=enp0s3
UUID=c8752366-3e1e-47e3-8162-c0435ec6d451
DEVICE=enp0s3
ONBOOT=yes
IPV6_PRIVACY=no

```

File /etc/resolv.conf

```
domain mydomain.com
search mytest.com
nameserver 192.168.1.1

```

## Command line tool

```
nmcli

nmcli con add type ethernet conname eth1 ifname enp0s3 ip4 10.0.2.10/24 gw4 192.168.1.254

```

## IP command options

| Parameter | Description |
| --- | --- |
| address | Display or set the internet protocol version 4 (Ipv4) or IPv6 address on the device |
| addrlabel | Define configuration labels |
| l2tp | Tunnel ethernet over IP |
| link | Define a network device |
| maddress | Define a multicast address for the system to listen to |
| monitor | watch for netlink messages |
| mroute | Define an entry in the multicast routing cache |
| mrule | Define a rule in the multicast routing policy database |
| neighbor | Manage Address Resolution Protocol (ARP) or IPv6 Neighbor Discovery (NDISC) cache entries |
| netns | Manage network namespaces |
| ntable | Manage the neighbor cache operation |
| route | Manage the routing table |
| rule | Manage entries in the routing policy database |
| tcpmetrics | Manage Transmission Control Protocol (TCP) metrics on the interface |
| Token | Manage tokenized interface identifiers |
| Tunnel | Tunnel over IP |
| Tuntap | Manage tunneled or tapped (TUN/TAP) devices |
| xfrm | Manage Internet Protocol Security (IPSec) policies for secure connections |

```
ip address add 10.0.2.15/24 dev enp0s3
ip route add default via 192.168.1.254 dev enp0s3
ip link set enp0s3 up

```

## Network troubleshooting commands

| command | Description |
| --- | --- |
| ping | traceroute ICMP packets |
| netstat | Lists all open network connections on the system |