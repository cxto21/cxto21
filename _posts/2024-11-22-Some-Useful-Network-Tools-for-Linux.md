---
title: Some Useful Network Tools for Linux
date: 2024-11-22 10H:16:00 -0300
categories: [Distributed Systems, Networks]
tags: [distributed-systems, networks, linux-network-tools]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/thumb/1/1f/Debian_Tux.png/640px-Debian_Tux.png
  alt: Picture
---

# Some Useful Network Tools for Linux

1. **nmap**
nmap is a tool mainly focused on network discovery, allows other operations such as how to act on network services and includes plugins and the ability to add functionality (as well as being an open source tool). It is used in network audits, for cybersecurity reasons, or to generate network inventories. The tool offers options to target and limit discovery and interactions. 

Discovery operations with nmap:**
* see about the system, versions, traceroute: "$> nmap -A -v {IP}/{MASK}"
* about the operating system: "$> nmap -O .."
* view exposed services at a specific address: "$> nmap -sV .."
* Scan without performing DNS resolution: "$> nmap -n .."
* view with DNS resolution: "$> nmap -R .."
* Skip ping assuming host is up: "$> nmap -Pn .."
* Scan on specific ports: "$> nmap -p(Ports) .."
* Host name discovery: "$> nmap -sL .."
* Quick scan of the 100 most common ports: "$> nmap -T4 -F .."
* High level of aggressiveness in scanning: "$> nmap -T4 .." 

Options to export:
* export in normal format: "$> nmap .. -oN"  
* export in XML format: "$> nmap .. -oX"  
* export in "'grep'eable" format: "$> nmap .. -oG"  


2. **netstat & ss**
netstat and ss are tools used to display network data and statistics, ss  for "socket statistics". They allow you to view information about open sockets, related processes, protocols used, connection status, more... SS is currently preferred along with the rest of the tools in the iproute2 package, netstat and the net-tools package are becoming obsolete.
*See on Linux more about netstat: "$> netstat {-V|--version|-h|--help}"|"man netstat"*

Summary of some basic functions of ss:
* See all sockets: "$> ss -a" 
* View listening sockets: "$> ss -l .." 
* See only IPv4 sockets: "$> ss -4 .."
* See only IPv6 sockets: "$> ss -6 .."
* See only UNIX sockets: "$> ss -x .."
* See only tcp sockets: "$> ss -t .."
* See only udp sockets: "$> ss -u .."
* View processes using sockets: "$> ss -p .." 
* View processes and sockets in SELinux context: "$> ss -z .." 

3. **ping**
It is mainly used to see if a server is on the network. It sends packets using IPv4/IPv6, the operation can be configured, it sends messages or not. The ttl of the packages can give us an indication of the operating system we are dealing with.      
*lista de TTL comunes*
* *Linux:* TTL: 64{TCP,UDP}
* *Windows 95,98,ME:* TTL: 32{TCP,UDP}
* *Windows X,7,8,..:* TTL: 128{TCP,UDP} 

*some options and uses*
* *ping simple infinity call:* *$> ping gmail.com*
* *ping max packages:* *$> ping -c7 gmail.com*
* *ping specify ttl:* *$> ping -t32 gmail.com*
* *ping ipv4:* *$> ping -4 ...*
* *ping IPV6:* *$> ping -6 ...*
* *ping IPV6:* *$> ping -6 ...*
* *ping without dns resolution:* *$> ping -n ...*

4. **traceroute**
With this tool we can try to follow the jumps between networks and systems that the packets make to reach their destination. It is not always possible to read this complete information as networks can be restricted and hops can be hidden.

*some options and uses*
* *traceroute simple call:* *$> traceroute gmail.com*
* *traceroute set initial distance hop:* *$> traceroute -f3 gmail.com*
* *traceroute specify port:* *$> traceroute -p632 gmail.com*
* *traceroute set maximal hop count:* *$> traceroute  -m92 gmail.com*


5. **dig**
dig allows to view the dns queries made by the host and address records.
*basic options and uses*
* *dig simple call:* *$> dig gmail.com*
* *dig use only ipv4:* *$> dig -4 gmail.com*
* *dig use only ipv6:* *$> dig -6 gmail.com*
* *dig especify port number:* *$> dig -p4 gmail.com*

6. **wireshark**
This tool is a network traffic viewer, it offers mechanisms to scan, filter scan, present searches and filter them. bluetooth networks, wifi, ethernet, loopback, together. In the tool you can see the packets in detail and it offers an organized presentation in the different tcp/ip layers. When a WiFi card is configured to monitor mode with Wireshark, it is possible to see the connections between access points (APs) and their connected users.

**Running wireshark on linux.**
*installation of wireshark: <a src="https//www.wireshark.org">official wireshark website</a>.*
* *Usage: wireshark [options] ... [ <infile> ]*
* *$> wireshark*: To run wireshark by entering the console in linux.
* *$> wireshark -k*: Wireshark execution and automatic capture. 
* *$> wireshark -I*: Capture in Monitor Mode if available 
* *$> wireshark -C*: Start wireshark with a specific configuration profile.
* *$> wireshark -r*: Open wiresehark by reading the specified file. pcap file  
* *$> wireshark -w 'output'*: Assign the output file, the argument "-" give the standard output.   
* *$> wireshark -r 'input'* ): Open wireshark by reading the specified file. pcap file  
* *$> wireshark -c*: End after n received packets.  

7. **burpsuite**
Burpsuite is proprietary software and its full version is paid, but it has a community version, it is mainly used for security audits.
The tool contains a proxy and offers a browser engine. By filtering as a proxy, it allows you to study requests and shipments between client and server. Burpsuite offers a suite of penetration testing tools such as vulnerability testing, dictionary entry, dos methods, and more.    
<a href="https://portswigger.net/burp" target="__blank">Link to Burpsuite</a>

8. **netcat**
* usage: nc [-46CDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl]
*some options and uses*
* *nc use :* "$> nc gmail.com"
* *nc use ipv4:* "$> nc -4 .."
* *nc use ipv6:* "$> nc -6 .."
* *nc use unix socket:* "$> nc -U .."
* *nc use udp:* "$> nc -u .."
* *nc set source address:* "$> nc -s .."
* *nc especify port number:* "$> nc -p4102 .."
*Example:*
  * "$> echo -en 'HTTP/1.1 200 OK\r\nContent-Type: text/htmls\r\n\r\n\sHyellouwaa-Cxto!' | nc -l -p 80"
