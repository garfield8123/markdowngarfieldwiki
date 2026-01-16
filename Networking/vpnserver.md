
# VPN Server

* Uses OPENVPN CloudConnexa to handle connections
* Public facing openvpn connection [more info](https://orangegarfieldspam01.openvpn.com)
* Connects to private facing IP address

## Private Network Address

* 192.168.0.1/24
* 192.168.2.1/24

## Network information

* 192.168.0.1/24 Internal network address space of all main home network devices
* 192.168.2.1/24 Internal network address space of all lab network devices

The network is subnet to ensure network traffic segmentation, but routes all traffic back to 192.168.0.1/24 network to ensure internet access