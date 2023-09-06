# Net Practice
This project is a System Administration related exercise

## Basics

### IP and IP address:
An **IP**, short for **Internet Protocol** is a set of rules, for routing and addressing packets of data.
 _Data traversing the Internet is divided into smaller pieces, called packets_.

An **IP address**, is an identifying number for network hardware connected to a network. Having an IP address allows a
device to communicate with other devices over an IP-based network like the internet._(Each internet device may have one
or more IP address)_

> There are 2 version of IP address: **IPv4** and **IPv6**. The former is the older version, while IPv6 is the upgrade
> IP version
- **IPv4** address:
	- 32 bits, usually written in 4 groups, each as a decimal, each decimal group represent 8 bits.
	_example_:
	```
	199.12.34.5
	```
	- The way IPv4 address are constructed means it's able to provide over 4 bilion unique IP addresses (2<sup>32</sup>)
- **IPv6** address:
	- 128 bits, usually written in 8 groups, each is 4 digits of hexadecimal, separated by colon, with leading 0
	  omitted, each group of hexadecimal represents 16 bits.
	_example_:
	```
	2001:db8:0:1234:0:567:8:1
	```
	- IPv6 supports 340 trillion, trillion, trillion addresses (2<sup>128</sup>). That's 340 with 12 zeros!

### Different types of IP addresses:
While all IP addresses are made up of numbers or letters, not all addresses are used for the same purpose. There are
specific types of IP addresses:
- **Public IP Address:**
	- Public IP addresses are used on hosts connected to the internet. Each public IPv4 address is unique on the
	  whole internet. Only public IP addresses are routable on the internet.
	- Although each public IP address is unique, we can have shared public IPs which are used by many hosts. This
	  sharing mechanism was created to conserve IP address space and is usually implemented using **NAT overload**. \
	  _(NAT **Network Address Translation** Overload, also know as PAT (Port Address Translation): The main purpose
	  of NAT is to hide the IP address (usually private) of a client in order to reserve the public address space)._

		- For example, your home network might have several internal client hosts (laptops, smartphones, etc) each having a
	private IP address. All these internal hosts share a single public IP which is assigned to the WAN interface of your
	home router device. Therefore, these internal hosts can now access the internet using the public IP of the router. 
