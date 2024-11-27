---
title: Linux access control
date: 2024-11-21 10H:16:00 -0300
categories: [Linux, Access Control]
tags: [linux, access-control, shell-script, bash, shell, users-on-linux]
author: 0
description:
image:
  path: https://i0.wp.com/www.junosnotes.com/wp-content/uploads/2021/07/Chown-Recursively-chown-recursive.png
  alt: Picture
---
![img-description](https://i0.wp.com/www.junosnotes.com/wp-content/uploads/2021/07/Chown-Recursively-chown-recursive.png){: w="700" h="500"}

# Linux access control 

*Resources limited by users and groups in Linux/Unix*
* In linux it is common to find users and groups by their group identifier and by their user identifier, "GID" and "UID" respectively.
* Root is the user with the highest privileges in the Unix Operative systems. Chroot allows "changing the root directory" of the system for a process and its children, this allows the creation of so-called "Chroot Jails" that are used to run a program and reduces the risk of exposing the real root directory. Doing this prevents the program from accessing resources "above" its assigned root directory.

*See more about existing Users and Groups: "$> cat /etc/passwd | less" ; "$> cat /etc/shadow"*
**User and group commands**
* Addgroup:
  * *Create a group:* groupadd  
  * *Assign password to a group:* "$> groupadd -p ['password'|enter and input password]"
  * *Assign group ID:* "$> group -g 'GID_desired' .."
* Add user:
  * *Create a user:* "$> adduser 'desiredName'" 
  * *Specify primary group:* "$> adduser -g 'grupoPrincipal' .."
  * *Specify secondary group:* "$> adduser -g 'primaryGroup' -G 'secondaryGroup'"

* Modify user:
  * *Change primary group:* "$> usermod -g 'desiredGroup' 'userName'"
  * *Change secondary group:* "$> usermod -a -G 'desiredGroup' 'userName'" *-a is for not remove the current group*
  * *Change password:* "$> passwd 'userName'", get into
  * *Re-assign user folder:* 
    * *Create dir:* "$> mkdir 'desiredFolderName'"
    * *Change directory owner :* "$> chown user:userG -R 'desiredFolderName'"
    * *Assign permissions:* "$> chmod 755 -R 'desiredName'"
    * *Change user folder:* "$> usermod -d 'desiredName' 'userName'"

**Firewall in linux:**
Increase restrictions and control over user applications and network services.
*ufw*, one of the firewalls in linux. *gufw*, graphic version of ufw.
* *Enable ufw (enable on boot):* "$> ufw enable"
* *check firewall:* "$> ufw status"
* *Query firewall enumerating:* "$> ufw status numbered"
* *Add rule deny by IP:* "$> ufw deny from 'IP]'"
* *Add rule deny by IP/mask:* "$> ufw deny from 'IP'/'MASK'"
* *Add rule allow by IP:* "$> ufw allow from 'IP'"
* *Add rule allow by IP/mask:* "$> ufw allow from 'IP'/'MASK'"
* *Delete rule:* "$> ufw delete 'ruleNumber'"
* *View available app profiles: "$> ufw app list"
* *Enable application profile:* "$> ufw allow 'CUPS'"
* *Enable service by your port:* "$> ufw allow 53"
* *Example rule:* "$> ufw allow from 'IP' proto udp to any port 2121"

**SSH Connections on Sistemas Linux**
* *Key Generation with SSH Keygen*
  * *Default:* "$> ssh-keygen"  
  * *Indicating algorithm:* "$> ssh-keygen -t [dsa|ecdsa|ecdsa-sk|ed25519|ed25519-sk|rsa]"
  * *Specify key format:* "$> ssh-keygen -m 'desiredFormat'"
  * *Change pass-phrase:* "$> ssh-keygen -p -f 'keyPath' -m 'format' -N 'desiredPhrase' -P 'currentPhrase'  

* *Connect to ssh server from linux:*
  * *Default connection:* "$> ssh [name | IP]" 
  * *Allow only IPv4:* "$> ssh -4 .." 
  * *Allow only IPv6:* "$> ssh -6 .." 
  * *Specify user name:* "$> ssh 'user'@['IP'|'domain']" 
  * *Specify port number:* "$> ssh .. -p 'portNumber' 
  * *Specify keyPath:* "$> ssh -i 'pathToKey' .."

* *Expose ssh on Linux*
  1. *Install openssh-server*: "$> aptinstall openssh-server"
  * *we enable the ssh service*: "$> systemctl enable ssh"
  * *start the service: "$> systemctl start ssh" 
  * *We review the status:* "$> systemctl status ssh"
  * *Restart the service:* "$> ssh service restart"
  * *to finish it:* "$> ssh service stop"
  * *Deny access to remote shell:* Add on "/etc/ssh/sshd_config"
    * Deny user: add "DenyUsers (users)" 
    * Deny group: add "DenyGroups (groups)"
