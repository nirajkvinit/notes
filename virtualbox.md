https://2buntu.com/articles/1513/accessing-your-virtualbox-guest-from-your-host-os/
use "ifconfig -a" to list all available network interfaces
edit /etc/network/interfaces file 

auto enp0s3
iface enp0s3 inet dhcp
pre-up sleep 2

auto enp0s8
iface enp0s8 inet static
	address 192.168.10.16
	netmask 255.255.255.0
