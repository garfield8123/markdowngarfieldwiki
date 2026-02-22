# Common COmmands

## Find all directories in website

### gobuster

```
gobuster -u http://fakebank.thm -w wordlist.txt dir

```
 
## Network Mapping

### Nmap

#### Common Command

```shell
sudo namp -sN -A <ip_address>
```

#### Passive

```shell
sudo nmap -T Sneaky <ip_address>
sudo nmap -sn <ip_address>
sudo nmap -sL <ip_address>
```

#### Semi-Passive

```shell
sudo nmap -Pn <ip_address>
sudo namp -sN <ip_address>
sudo nmap -sT <ip_address>
sudo nmap -S <spoof_ip_address> <ip_address> -e <interface_name>  
sudo nmap --spoof-mac <mac_address> <ip_address>
```

#### Active

```shell
sudo namp -A <ip_address>
sudo nmap -sU <ip_address>

```