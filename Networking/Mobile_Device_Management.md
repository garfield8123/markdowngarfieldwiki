
# Mobile Device Management

## Miradore Device Management

Mobile Device Management to manage my laptop and vms easily

* [Miradore](https://online.miradore.com/garfield8123/)

## Fleet MDM Local Server

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