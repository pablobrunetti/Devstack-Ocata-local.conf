# Devstack-Ocata-local.conf
This repository contains a local.conf script which can be used to create a devstack Ocata setup. The monitoring modules of the Devstack is working(Gnocchi + ceilometer + AODH). 

# Pre-requisites
Start with a clean and minimal install of a Linux system. Devstack attempts to support Ubuntu 16.04/17.04, Fedora 24/25, CentOS/RHEL 7, as well as Debian and OpenSUSE.

If you do not have a preference, Ubuntu 16.04 is the most tested, and will probably go the smoothest.

# Configuration
These are some of the key changes to be made in local.conf

HOST_IP: This should be the IP of where where you're running devstack. HOST_NAME: Same as above but hostname instead of IP Address.

# HowTo run

## Add Stack User

Devstack should be run as a non-root user with sudo enabled (standard logins to cloud images such as “ubuntu” or “cloud-user” are usually fine).

You can quickly create a separate stack user to run DevStack with

``` $ sudo useradd -s /bin/bash -d /opt/stack -m stack ```

## Since this user will be making many changes to your system, it should have sudo privileges:

``` $ echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack 
    $ sudo su - stack 
```
## Update packages
```
   # sudo apt-get update
   # sudo apt-get install aptitude build-essential git ntp ntpdate   openssh-server python-dev sudo
```

## Download DevStack
``` $  git clone https://git.openstack.org/openstack-dev/devstack -b stable/ocata
    $ cd devstack
```    
## Create a local.conf



