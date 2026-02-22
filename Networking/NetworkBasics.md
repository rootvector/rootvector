# 🌐NETWORK BASICS FOR HACKERS

*by occupyTheWeb*

------------------------------------------------------------------------

# 📘 CHAPTER 1 -- NETWORK BASICS

------------------------------------------------------------------------

## 🌍 IP Address (Internet Protocol Address)

Each digital device (computer, laptop, phone, tablet, etc.) is assigned
an IP address.\
This enables devices to communicate and connect with each other.

Think of an IP address like your home address.\
Without it, no one could find you and send you mail.

------------------------------------------------------------------------

### 🔹 Types of IP Addresses

-   **IPv4**
-   **IPv6**

### 🔹 IPv4 Structure

IPv4 is made up of:

-   **32 bits**
-   Divided into **4 octets**
-   Each octet = 8 bits

4 × 8 = 32 bits (or 4 bytes)

**Example:**

    172.16.254.1

------------------------------------------------------------------------

## 🏷 Classes of IP Addresses (Legacy Concept)

-   **Class A:** 0.0.0.0 -- 127.255.255.255\
-   **Class B:** 128.0.0.0 -- 191.255.255.255\
-   **Class C:** 192.0.0.0 -- 223.255.255.255

> Note: Modern networking uses CIDR instead of classful addressing.

------------------------------------------------------------------------

## 🔐 Private vs Public IP Addresses

### 🔹 Private IP Addresses

Private IPs communicate only within a **LAN (Local Area Network)**.

They cannot directly access the internet.

**Private IP ranges:**

-   10.0.0.0 -- 10.255.255.255\
-   172.16.0.0 -- 172.31.255.255\
-   192.168.0.0 -- 192.168.255.255

------------------------------------------------------------------------

### 🔹 Public IP Addresses

Public IPs are routable over the **WAN (Wide Area Network)** (the
Internet).

To access the internet:

> Private IP must be translated into a Public IP using NAT.

------------------------------------------------------------------------

### 🔹 Check IP in Linux

    ifconfig

Or:

    ip a

------------------------------------------------------------------------

## 📡 DHCP -- Dynamic Host Configuration Protocol

DHCP automatically assigns IP addresses to devices on a network.

This means: - Your IP may change over time - It is assigned dynamically

------------------------------------------------------------------------

## 🔄 NAT -- Network Address Translation

NAT translates **private IP addresses** into a **public IP address** so
they can communicate over the internet.

### 🔹 Why NAT Exists

Private IP addresses: - Work only inside LAN - Are not routable on the
internet

NAT device (usually your router): - Translates private → public -
Maintains a NAT table - Tracks which internal device requested what

When response comes back: - NAT checks its table - Forwards packet to
correct internal device

------------------------------------------------------------------------

## 🚪 Ports -- The Doors of a House for Hackers

An IP address is the primary address.\
A port is like a sub-address.

Total number of ports:

**65,536 (2¹⁶)**

------------------------------------------------------------------------

### 🔹 Port Ranges

-   0--1023 → Well-known ports\
-   1024--49151 → Registered ports\
-   49152--65535 → Ephemeral (dynamic) ports

------------------------------------------------------------------------

### 🔥 Important Ports Hackers Must Know

  Port      Service   Protocol
  --------- --------- ----------
  21        FTP       TCP
  22        SSH       TCP
  23        Telnet    TCP
  25        SMTP      TCP
  53        DNS       TCP/UDP
  67/68     DHCP      UDP
  80        HTTP      TCP
  110       POP3      TCP
  137-139   NetBIOS   TCP/UDP
  143       IMAP      TCP
  161/162   SNMP      UDP
  389       LDAP      TCP/UDP
  443       HTTPS     TCP
  445       SMB       TCP
  3389      RDP       TCP/UDP

------------------------------------------------------------------------

### 🔎 Scanning Ports with Nmap

    sudo nmap -sT <target IP>

-   `-sT` = TCP Connect scan

------------------------------------------------------------------------

## 📦 TCP/IP -- Transmission Control Protocol & Internet Protocol

Understanding TCP/IP is essential for building hacking tools and
analyzing attacks.

------------------------------------------------------------------------

### 🔹 What Are Protocols?

A protocol is a set of rules that devices follow to communicate over a
network.

Protocols define:

-   Format of data
-   Order of communication
-   Error handling
-   Session management

Most protocols are defined in:

**RFC (Request for Comments)**

------------------------------------------------------------------------

### 🔹 Important Protocols

-   TCP
-   IP
-   UDP
-   HTTP
-   HTTPS
-   SMTP
-   FTP
-   DNS

------------------------------------------------------------------------

## 🌍 IP -- Internet Protocol

IP is responsible for:

-   Defining source IP address
-   Defining destination IP address
-   Routing packets across networks

IP handles addressing.\
TCP handles reliable communication.

Together: **TCP/IP**

**IP PACKET HEADER**

**Row 1*

- varsion: IPv4 or IPv6
- IHL: length of header
- Type Of Serivece (TOS): Define the Type of service of this packet.
- Total Length: define total lenght of the IP datagram (including data) or the fragment. MAX **65535**.


**Row 2**

- Identification: uniquely identifies ecah packet. use for reassembling fragmented packts.
- IP Flags: This field defines whether the packet is fragmented (M) or not (D). The manipulation of the field can be used to evade IDS and firewalls.
- Fragment Offset: This field is used when packets are fragmented. It defines where the packets should be reassembled from the beginning of the IP header.

**Row 3**

- TTL (TIME TO LIVE): this field define how many hops across the internet before the packet expires. *it helpful to identify the OS of the sender*.
- Protocol: This field defines what protocal is being used with IP. Most often, it will be 6 or TCP, 1 FOR ICMP, 17 FOR UDP, among other.
- Header Checksum: this is an error-checking field. It calculates the checksum (a simple algorithm) to determine the integrity of the data in the header.

**Rows 4 & 5**

- Source / Destination: These rows of the IP header are probably the most important part of the header as it contains the source and destination IP address.
    
**Row 6**

- Options: This field is variable in length, and its use is optional (as you might expect).
- Padding: This field is used to fill out, if necessary, the remaining bits and bytes of the header.

-------------------------------------------------------------------------------------------------------------

## 📦 TCP Header Fields (Important for Hackers)

## 🔹 Row 1 – Ports
- **Source Port** → Where the communication came from  
- **Destination Port** → Where the communication is going  

These determine which service/process is sending and receiving data.

---

## 🔹 Row 2 – Sequence Number
- Generated by the sender’s TCP stack  
- Ensures packets are reordered correctly on arrival  
- Critical for reliability  
- Plays a role in MitM attack resistance  

---

## 🔹 Row 3 – Acknowledgment Number
- Confirms receipt of data  
- Receiver sends back ACK with expected next sequence number  
- If no ACK is received, sender retransmits  

✔ This is why TCP is reliable  
❌ UDP does not use acknowledgments (unreliable)

---

## 🔹 Row 4 – TCP Flags (Very Important)

### Main Flags:
- **SYN** → Start connection  
- **FIN** → Graceful close  
- **ACK** → Acknowledgment  
- **RST** → Force close / wrong port  
- **URG** → Urgent data present  
- **PSH** → Push data immediately to application  

> Tools like nmap and hping3 manipulate these flags for stealth scans and firewall evasion.

### Window Size
- Controls how much data can be buffered  
- Used for flow control  
- Helps in OS fingerprinting  
- Used by tools like **p0f**

---

## 🔹 Row 5
- **Checksum** → Error detection (integrity check)  
- **URG Pointer** → Points to urgent data (used with URG flag)

---

## 🔹 Row 6
- **Options** → Extra configuration (variable length)  
- **Padding** → Ensures header is multiple of 32 bits  

---
