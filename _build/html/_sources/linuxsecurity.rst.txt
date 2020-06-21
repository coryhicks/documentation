..  _LinuxSecurity:

# documentation

$LinuxSecurity
===========

NMAP
----

- https://highon.coffee/blog/nmap-cheat-sheet/

- Find open/exposed Netbios Servers

	$ nmap -sV -v -p 139,445 192.168.0.0/24

- Enumerate SMB Users

	$ nmap -sU -sS --script=smb-enum-users -p U:137,T:139 192.168.0.200-254

NBTSCAN
-------

- Find Windows / Samba servers on subnet, returns mac address, netbios name, client workgroup domain

	$ nbtscan 192.168.0.0/24

NIKITO
------

- https://cirt.net/Nikto2

- For http/https web server enumeration

	$ nikto -h 192.168.0.100

NETSTAT
-------

- See Open Ports

	$ sudo netstat -tulpn | grep LISTEN

SSH Attempted Logins
--------------------
- https://www.suse.com/c/checking-log-file-invalid-ssh-connection-attempts/

	$ grep "Invalid user" /var/log/messages

	$ grep "Invalid user" /var/log/messages|awk '{print $NF}' | \ sort|uniq -c|sort -nr|head -n 25
