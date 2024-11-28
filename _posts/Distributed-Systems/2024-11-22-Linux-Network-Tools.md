---
title: Linux Network Tools
date: 2024-11-22 10H:21:00 -0300
categories: [Distributed Systems, Networks]
tags: [distributed-systems, networks, standard-ports]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/7/73/Logo_nmap.png?20230731104508
  alt: Picture
---

# Linux Network Tools

1. **nmap**

  nmap is a tool mainly focused on network discovery, allowing other operations such as acting on network services. It includes plugins and the ability to add functionality (as well as being an open-source tool). It is used in network audits, for cybersecurity reasons, or to generate network inventories. The tool offers options to target and limit discovery and interactions.

  **Discovery operations with nmap:**
  - See system details, versions, traceroute: `$ nmap -A -v {IP}/{MASK}`
  - Identify the operating system: `$ nmap -O ..`
  - View exposed services at a specific address: `$ nmap -sV ..`
  - Scan without performing DNS resolution: `$ nmap -n ..`
  - View with DNS resolution: `$ nmap -R ..`
  - Skip ping assuming host is up: `$ nmap -Pn ..`
  - Scan specific ports: `$ nmap -p(Ports) ..`
  - Host name discovery: `$ nmap -sL ..`
  - Quick scan of the 100 most common ports: `$ nmap -T4 -F ..`
  - High level of aggressiveness in scanning: `$ nmap -T4 ..`

  **Options to export:**
  - Export in normal format: `$ nmap .. -oN`
  - Export in XML format: `$ nmap .. -oX`
  - Export in "grepable" format: `$ nmap .. -oG`

2. **netstat & ss**

  netstat and ss are tools used to display network data and statistics, with ss standing for "socket statistics". They allow you to view information about open sockets, related processes, protocols used, connection status, and more. SS is currently preferred along with the rest of the tools in the iproute2 package, as netstat and the net-tools package are becoming obsolete.

  **See more about netstat on Linux:**
  - `$ netstat {-V|--version|-h|--help}` or `man netstat`

  **Summary of some basic functions of ss:**
  | Command    | Description                                   |
  | ---------- | --------------------------------------------- |
  | `ss -a`    | See all sockets                               |
  | `ss -l ..` | View listening sockets                        |
  | `ss -4 ..` | See only IPv4 sockets                         |
  | `ss -6 ..` | See only IPv6 sockets                         |
  | `ss -x ..` | See only UNIX sockets                         |
  | `ss -t ..` | See only TCP sockets                          |
  | `ss -u ..` | See only UDP sockets                          |
  | `ss -p ..` | View processes using sockets                  |
  | `ss -z ..` | View processes and sockets in SELinux context |

3. **ping**

  ping is mainly used to see if a server is on the network. It sends packets using IPv4/IPv6, and the operation can be configured to send messages or not. The TTL of the packets can give an indication of the operating system we are dealing with.

  **Common TTL values:**
  - Linux: TTL: 64 (TCP, UDP)
  - Windows 95, 98, ME: TTL: 32 (TCP, UDP)
  - Windows XP, 7, 8, etc.: TTL: 128 (TCP, UDP)

  **Some options and uses:**
  - Simple infinite ping: `$ ping gmail.com`
  - Ping with a maximum number of packets: `$ ping -c7 gmail.com`
  - Ping with specified TTL: `$ ping -t32 gmail.com`
  - Ping using IPv4: `$ ping -4 ...`
  - Ping using IPv6: `$ ping -6 ...`
  - Ping without DNS resolution: `$ ping -n ...`

4. **traceroute**

  traceroute is used to follow the hops between networks and systems that packets make to reach their destination. It is not always possible to read this complete information as networks can be restricted and hops can be hidden.

  **Some options and uses:**
  - Simple traceroute call: `$ traceroute gmail.com`
  - Set initial distance hop: `$ traceroute -f3 gmail.com`
  - Specify port: `$ traceroute -p632 gmail.com`
  - Set maximal hop count: `$ traceroute -m92 gmail.com`

5. **dig**

  dig allows viewing the DNS queries made by the host and address records.

  **Basic options and uses:**
  - Simple dig call: `$ dig gmail.com`
  - Use only IPv4: `$ dig -4 gmail.com`
  - Use only IPv6: `$ dig -6 gmail.com`
  - Specify port number: `$ dig -p4 gmail.com`

6. **wireshark**

  Wireshark is a network traffic viewer that offers mechanisms to scan, filter scans, present searches, and filter them. It supports Bluetooth networks, WiFi, Ethernet, and loopback. In the tool, you can see the packets in detail and it offers an organized presentation in the different TCP/IP layers. When a WiFi card is configured to monitor mode with Wireshark, it is possible to see the connections between access points (APs) and their connected users.

  **Running Wireshark on Linux:**
  - Installation: [official Wireshark website](https://www.wireshark.org)
  - Usage: `wireshark [options] ... [ <infile> ]`
  - Run Wireshark: `$ wireshark`
  - Automatic capture: `$ wireshark -k`
  - Capture in Monitor Mode if available: `$ wireshark -I`
  - Start with a specific configuration profile: `$ wireshark -C`
  - Open Wireshark by reading the specified file (pcap file): `$ wireshark -r 'input'`
  - Assign the output file: `$ wireshark -w 'output'`
  - End after n received packets: `$ wireshark -c`

7. **burpsuite**

  Burpsuite is proprietary software with a paid full version, but it has a community version. It is mainly used for security audits. The tool contains a proxy and offers a browser engine. By filtering as a proxy, it allows you to study requests and shipments between client and server. Burpsuite offers a suite of penetration testing tools such as vulnerability testing, dictionary entry, DoS methods, and more.

  [Link to Burpsuite](https://portswigger.net/burp)

8. **netcat**

  netcat is a versatile networking tool.

  **Usage:**
  - `nc [-46CDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl]`

  **Some options and uses:**
  - Simple use: `$ nc gmail.com`
  - Use IPv4: `$ nc -4 ..`
  - Use IPv6: `$ nc -6 ..`
  - Use UNIX socket: `$ nc -U ..`
  - Use UDP: `$ nc -u ..`
  - Set source address: `$ nc -s ..`
  - Specify port number: `$ nc -p4102 ..`

  **Example:**
  - `$ echo -en 'HTTP/1.1 200 OK\r\nContent-Type: text/html\r\n\r\nHello-Cxto!' | nc -l -p 80`
