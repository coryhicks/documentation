..  _networking:

# documentation

$networking
===========

Basic Tasks
-----------

Static IP
---------

Ubuntu:

- Ubuntu uses netplan after version 18 and up, it's pretty easy to use, you will need the name of your network interface::
	
	$ ip a

- use vi or other text editor to edit the .yaml file here: /etc/netplan

.. NOTE:: here is a sample static ipv 4 example

		network:
		  version: 2
		  renderer: networkd
		  ethernets:
		    ens33:
		      dhcp4: no
		      addresses:
		        - 172.16.0.100/24
		      gateway4: 172.16.0.1
		      nameservers:
		          addresses: [8.8.8.8, 1.1.1.1]



- make sure you have all the tools you need, ifconfig, etc


- disable ipv6::

	$ sudo sysctl -w net.ipv6.conf.eth0.disable_ipv6=1

- add to /etc/sysctl.conf::

	$ net.ipv6.conf.eno0.disable_ipv6=1

see what ports are open for a specific service::

	$ ss -tulnp | grep "rsyslog"


DHCP
----

- Config File:

	/etc/dhcp/dhcpd.conf

- Fresh install creates empty dir, copy sample to /etc/dhcp/::

	$ sudo \cp /usr/share/doc/dhcp-server/dhcpd.conf.example /etc/dhcp/dhcpd.conf

- Service::

	$ systemctl enable dhcpd (to start at boot-up)
	$ systemctl status/start/stop/restart dhcpd

- View open leases::

	$ egrep "lease|hostname|hardware|\}" /var/lib/dhcpd/dhcpd.leases
	

Fedora
------

Fedora and CentOS use firewalld.

firewall to allow dns qrys::

    $ sudo firewall-cmd --zone= --add-service=dns

Open up port in firewall::

	$ firewall-cmd --permanent --zone=public --add-service=http

	$ firewall-cmd --reload

Ubuntu
------

User Friendly Firewall (UFW).

You need to enable the ufw service::
	
	$ sudo ufw enable

Allow web traffic on port 80 for http::

	$  sudo ufw --dry-run allow http

Allow traffic from a specific IP, this example allows ssh from a specific host::


	$ sudo ufw allow proto tcp from 172.16.0.2 to any port 22

Get status on the firewall::

	$ sudo ufw status verbose

Ufw uses profiles for popular applications, save yourself some time and see if what you need all ready has a profile::

	$ sudo ufw app list

For more info on ufw, check out the docs at Ubuntu - https://ubuntu.com/server/docs/security-firewall

.. warning::

	May need: setenforce Permissive, please research to see the negative security implications for this


Contribute
----------

- Issue Tracker: github.com/$project/$project/issues
- Source Code: github.com/$project/$project

Support
-------

If you are having issues, please let us know.
We have a mailing list located at: project@google-groups.com

License
-------

The project is licensed under the BSD license.