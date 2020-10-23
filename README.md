# nginx-HA

This vagrant will install 6 Ubuntu 18.04 machines, 2x Nginx webserver, 2x DB servers and 2x ubuntu server for Nginx loadbalancing.
It will add some default users, groups and directory's. By default 3 webservers with no content.
This Vagrant is to practice with Loadbalancing and High availability.
This repository is intended for educational purpose only.


## Prerequisites

Works on Windows 10 and tested on macOS (macOS needs the Virtualbox extension pack).

Software needed:
* Virtualbox 5.0 or higher
* Git bash for Windows
* Vagrant 2.2.6 or higher


## Demo installation && use Vagrant

Youtube: https://youtu.be/KABnIuaA8SM


## Demo loadbalancing with Nginx

Youtube: 


## Installation

* Install Virtualbox: https://www.virtualbox.org/wiki/Downloads
* Install Git bash for Windows: https://gitforwindows.org/
* Install Vagrant for Windows: https://www.vagrantup.com/downloads.html

## Run this Vagrant VM
Open **Git Bash** in Windows
```
cd Documents
mkdir vagrant && cd vagrant
git clone https://github.com/borahuho/nginx-HA
cd nginx-HA
vagrant up
```
## Mission

Read your mission in "Opdracht"

## Network
Vagrant VM will be set up with 2 network adapters
```
Nat : DHCP
Localhost (lb01): 192.168.10.200

Nat : DHCP
Localhost (lb01): 192.168.10.201

Nat : DHCP
Localhost (web1): 192.168.10.210

Nat : DHCP
Localhost (web2): 192.168.10.211

Nat : DHCP
Localhost (db1): 192.168.10.220

Nat : DHCP
Localhost (db2): 192.168.10.221
```
## Vagrant commands
Start VM's with Vagrant
```
vagrant up
```
Pause a VM
```
vagrant suspend
```
Restart a paused VM
```
vagrant resume
```
Stop and shutdown a VM
```
vagrant halt
```
Remove a VM
```
vagrant destroy
```
ssh in to the VM
```
vagrant ssh lb01
vagrant ssh lb02
vagrant ssh web01
vagrant ssh web02
vagrant ssh db1
vagrant ssh db2
```

