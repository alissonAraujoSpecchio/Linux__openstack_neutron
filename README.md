# Linux__openstack_neutron
Steps to install and configure openstack neutron, with some notes

## Installation

Just follow the steps in the link bellow:

https://docs.openstack.org/neutron/latest/install/controller-install-ubuntu.html

## Configure Network

This link is in one of the steps of the installation.

<br>

https://docs.openstack.org/neutron/latest/install/controller-install-option2-ubuntu.html

_notes:_

  1. To configure _net.bridge.bridge-nf-call-iptables_ edit, or create, this file:

  ```
  vim /etc/sysctl.d/bridge.conf
  ```
  
  And add this content:

  ```
  net.bridge.bridge-nf-call-iptables=1
  net.bridge.bridge-nf-call-ip6tables=1
  ```
  
  2. Enable br_netfilter
  
  ```
  sudo modprobe br_netfilter
  sudo sh -c 'echo "br_netfilter" > /etc/modules-load.d/br_netfilter.conf'
  ```
