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
	- These are used on the outside of a network and are assigned by an ISP _Internet Service Provider_. It's the main
	  address that a home or business network uses to communicate with the rest of the networked devices around the
	  world.
	  whole internet. Only public IP addresses are routable on the internet.
	- Although each public IP address is unique, we can have shared public IPs which are used by many hosts. This
	  sharing mechanism was created to conserve IP address space and is usually implemented using **NAT overload**. \
	  _(NAT **Network Address Translation** Overload, also know as PAT (Port Address Translation): The main purpose
	  of NAT is to hide the IP address (usually private) of a client in order to reserve the public address space)._

		- For example, your home network might have several internal client hosts (laptops, smartphones, etc) each having a
	private IP address. All these internal hosts share a single public IP which is assigned to the WAN interface of your
	home router device. Therefore, these internal hosts can now access the internet using the public IP of the router. \
		_WAN : a wide-area network is a collection of local-area networks (LANs) or other networks that communicate with
	one another. A WAN is essentially a network of networks, with the Internet the world's largest WAN._ 
- **Private IP Address:**
	- These are used inside a network. These types of IP addresses provide a way for devices to communicate with a
	  router and the other devices on the private home network. Private IP addresses can be set manually or assigned
	  automatically by the router.
- **Dynamic/Static ip:**
	- Private IP and public IP are either dynamic or static, which means that, respectively, they either change or they
	  don't.
	- An IP address that is assigned by a DHCP server is a dynamic IP. If a device doesn't have DHCP enabled or doesn't
	  support DHCP, then the IP address must be assigned manually, in which case it's called a static IP address.
		- Dynamic IP:
			- Always keep changing. It is temporary and are allocated to a device every time it
		connects to the web. 
		- Static IP:
			- A static IP address is configured to a device by an administrator and is fixed on the device (it does not
			  change)
			- Static IP address never changes, but it can be altered as part of routine network administra		tion.

- **Local Host IP (Loopback IP):**
	- All computers have a localhost IP which is the number *127.0.0.1*.
	- The corresponding IPv6 localhost address is *::1*.
	- If you acces "http://localhost or 127.0.0.1" in the browser, the request will not be forwarded to the internet through the
	  router, but will instead remain in your own system.


### IP Address Structre:

- IP address are divided into 2 parts: network and host; The beginning bits are the network, the rest are host.
- The reason IP address is divided into network and host parts is because it makes routing much more efficient. Similar
  to a home address is divided into Country, State/Province, City, then finally street address.
  - The network address is used to find the subnet in which the device is located.
  - The host address is used to find the computer or the device in the subnet.

### IPv4 Address Classes:

- Internet Protocol hierarchy contains several classes of IP Addresses to be used efficiently in various situations as
  per the requirement of hosts per network.
- The IPv4 addressing system is divided into five classes of IP addresses. All the five classes are indentified by the
  first octet of IP Address.
	- **Class A:**
		- Class A addresses are for networks with large number of total hosts.
		- The first bit of the first octet is always set to 0. Thus the first octet ranges from 1 - 127.
		```
		00000001 - 01111111
			   1 - 127
		```
		- The remaining three octets represent the hosts ID and allows for approximately 17 million
		hosts per network.
		- Class A addresses only include IP starting from 1.x.x.x to 126.x.x.x only. The IP range 127.x.x.x is reserved
		  for loopback IP addresses.
		- The default subnet mask for Class A IP address is 255.0.0.0 which implies that Class A addressing can have 126
		  networks (2<sup>24</sup> - 2).
		- Public IP Range: 1.0.0.0 to 127.0.0.0
			- First octet value range from 1 to 127
		- Private IP Range: 10.0.0.0 to 10.255.255.255
		- Number of networks: 126
		- Number of Hosts per Network: 16,777,214
		- Class A IP address format:
		```
		0NNNNNNN.HHHHHHHH.HHHHHHHH.HHHHHHHH
		```
	- **Class B:**
		- Class B addresses are for medium to large sized networks, it allows for 16384 networks by using the first two
		  octets for the network ID. The first two bits in the first octet are always 1 0. The remaining six bits,
		  toghether with the second octet, complete the network ID. The 16 bits in the third and fourth octet represent
		  host ID and allows for approximately 65000 hosts per network.
		- Class B network number values begin at 128 and end at 191.
		```
		10000000 - 10111111
			 128 - 191
		```
		- Public IP Range: 128.0.0.0 to 191.255.0.0
			- First octet value range from 128 to 191
		- Private IP Range: 172.16.0.0 to 173.31.255.255
			- Private APIPA Range: 169.254.0.0 to 169.254.255.255
				- APIPA: Automatic Private IP Addressing is a feature with MICROSOFT Windows-based computers to
				  automatically assign itself an IP address within this range if a DHCP server is not available on the
				  network.
		- Subnet Mask: 255.255.0.0 (16 bits)
		- Number of Networks: 16382
		- Numebr of Hosts per Network: 65534
		- Class B IP address format is:
		```
		10NNNNNN.NNNNNNNN.HHHHHHHH.HHHHHHHH
		```
	- **Class C:**
		- Class C addresses are used in small locla area networks (LANs). Class C allows for approximately 2 million
		  networks by using the first three octets for the network ID.
		- In a Class C IP address, the first three bits of the first octet are always 1 1 0;
		and the remaining 21 bits of first three octets complete the network ID. The last octet (8 bits) represent the
		host ID and allows for 254 hosts per network. Class C network number values begins at 192 and end at 223.
		```
		11000000 - 11011111
			 192 - 223
		```
		- Public IP Range: 192.0.0.0 to 223.255.255.0
			- First octet value range from 192 to 223
		- Private IP Range: 192.168.0.0 to 192.168.255.255
		- Subnet Mask: 255.255.255.0 (24 bits)
		- Number of networks: 2,097,150
		- Number of hosts per network: 254
		- Class C IP address format is:
		```
		110NNNNN.NNNNNNNN.NNNNNNNN.HHHHHHHH
		```
	- **Class D:**
		- Class D IP addresses are not allocated to hosts and are used for multicasting;
		Multicasting allows a single host to send a single stream of data to thousands of hosts across the internet at
		the same time. It is often used for audio and video streaming, such as IP-based cable TV networks.
		- Very first four bits of the first octet in Class D IP addresses are set to 1110.
		```
		11100000 - 11101111
			 224 - 239
		```
		- Range: 224.0.0.0 to 239.255.255.255
			- First octet value range from 224 to 239
		- Number of Networks: N/A
		- Number of Hosts per network: Multicasting

	- **Class E:**
		- Class E IP addresses are not allocated to hosts and are not available for general use. These are reserved for
		  research purposes.
		- Range: 240.0.0.0 to 255.255.255.255
			- First octet value range from 240 to 255
		- Number of networks: N/A
		- Number of hosts per network: Research/Reserved/Experimental 
### Subnet Mask:

- To separate network addresses from host addresses, IPv4 uses an additional component with IP addresses. This component
  is know as a *subnet mask*.
- An IP address is always used with the subnet mask. Without the subnet mask, an IP address is considered an ambiguous
  address.
- Bitmask/Subnet mask is used to indicate how many bits are the network part. The network bit are 1, and host bits are
  0.
- If a IP address has a bitmask of 255.255.0.0, it means the first 16 bits of IP address is network , and rest the host.
- There are 2 different ways of writing the mask:
	- Dot-decimal notation:
	```
	  -------------------------------------
	  |11111111.11111111.00000000.00000000|
	  -------------------------------------
	  |255     |255     |0       |0       |
	  -------------------------------------
	``` 
	- Class Inter-Domain Routing or CIDR:
		- Is used to indicate how many bits in the beginning of a IP address are network.
		- CIDR notation is like:
		```
		<x> . <x> . <x> . <x>	  /  	<n>
		'--------------------'         '---'
		           	^               ^
  				|               |
			dotted decimal		|
			notation for IP		|
  					is the number of
  					bits for network
  					part.
		```
