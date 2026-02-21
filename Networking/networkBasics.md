# NETWORKING BASICS FOR HACKERS

*by occupyTheWeb*

---
# CHAPTER 1 - NETWORK BASICS

## IP Addresss (INTERNET PROTOCOL ADDRESS)

Each digital device (computer, laptop, phone, tablet, etc.) is assigned an IP address, and this is
what enables us to communicate and connect with it. Imagine an IP address as being similar to
your house address. Without that address, no one could find you and send you snail mail.

**Types**

*IPv4 & IPv6*

It is made up of 32 bits of four octets (8 characters) or four groups of 8 bits (on/off switches).

**example**

*172.16.254.1*

4X8 = 32 bit, or 4 bytes


## Classes of IP Addresses

- Class A: 0.0.0.0 - 127.255.255.255
- Class B: 128.0.0.0 - 191.255.255.255
- Class C: 192.0.0.0 - 223.255.255.255

## Private vs Public IP Addresses

Private only communicate in LAN *(local area network)*.

**Private addresses include:**

- 192.168.0.0 - 192.168.255.255
- 10.0.0.0 - 10.255.255.255
- 172.16.0.0 - 172.16.255.255

On linux you can check your internet configuration using command: `ifconfig`

> Your Private IP address must be translated to a Public IP by NAT Device *(NETWORK ADDRESS TRANSLATION)*. to communicate over the public internet WAN *(WIDE AREA NETWORK)*.

## DHCP - *DYNAMIC HOST CONFIGURATION PROTOCOL*

The DHCP assign IP addresses dynamically. that means that you do not have the same IP address all of the time.


## NAT - *NETWORK ADDRESS TRANSLATION*

NAT is a protocol which translate a private IP addresses to external Public IP addresses that can route on the internte.

> Private IP Addresses : only communicate over LAN, does not able to communicate over the internet. you need to translate the private IP to Public IP address using NAT.

> NAT use NATTABLE to record the machine's both IP addresses, when packet return it will use that table to send that packet to requested machine.


## Ports - *The doors of a house for hackers*

Port is a king of sub-address. The IP is the Primary Address.

There are **65536** (2 raised to the 16th power) ports.

> The, 1024 are generally referred to as the *"common ports"*.

*Used by survices like,
    - ssh: 22
    - ftp: 21
    - http: 80
    - https: 443*

** Some Common Ports Hacker Need to Know by heart **

| Port Number(s) | Protocol | Port Type |
|:--------------:|:--------:|:---------:|
|   21           | FTP      | TCP, UDP  |
|   22           | SSH      | TCP, UDP  |
|   23           | TELNET   | TCP, UDP  |
|   25           | SMTP     |TCP, UDP   |
|   53           | DNS      | TCP, UDP  |
|   67/68        |DHCP      |UDP        |
|   80           | HTTP     | TCP, UDP  |
|   110          | POP3     | TCP, UDP  |
|   137-139      |NetBIOS/NetBT| TCP, UDP|
|   143          |IMAP      | TCP       |
|   161/162      |SNMP      | TCP, UDP  |
|   389          |LDAP      | TCP, UDP  |
|   427          | SLP      | TCP, UDP  |
|   443          | HTTPS    | TCP, UDP  |
|   445          | SMB/CIFS | TCP       |
|   548          | AFP      | TCP       |
|   3389         | RDP      | TCP, UDP  |


*we can use tool such as nmap to see what port are open on a system*

*example*

```bash
sudo nmap -sT <IP address of the target>
```

## TCP/IP - *TRANSMISSION CONTROL PROTOCOL & INTERNTE PROTOCOL*

> When trying to create a new hacking tool or investigate a network attack, understanding these protocols and their fields is essential. Otherwise, you will simply be wasting your time.

### What Are Protocols?

Protocols are simply an agreed-upon way to commnunicate. Protocal is a set of *rules* that host need to follow to communicate over the network.
Protocols are similar. A protocol simply defines a way of communication with all its rules. These
rules are usually defined by an RFC (Request for Comments).

*some Protocols are*

- TCP
- IP
- UDP
- HTTP
- HTTPS
- SMTP
- FTP,etc

**Most Importent Protocals for use over the internet are IP and TCP**

### IP - *internet protocol*

That is used to define the source and destination IP addresses of a packet as it travel the internet. It used in conjunction with other protocols such as TCP; the often-used conjuction, TCP/IP.


