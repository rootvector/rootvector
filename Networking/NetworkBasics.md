# 🌐 NETWORKING BASICS FOR HACKERS

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
