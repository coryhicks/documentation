..  _networking:

# documentation

$networking
===========

$networking will solve your problem of where to start with documentation,
by providing a basic explanation of how to do it easily.

Look how easy it is to use:

    import networking
    # Get your stuff done
    networking.do_stuff()

Basic Tasks
-----------

- set-up static ip

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

	egrep "lease|hostname|hardware|\}" /var/lib/dhcpd/dhcpd.leases
	

General Firewall 
----------------

firewall to allow dns qrys::

    $ sudo firewall-cmd --zone= --add-service=dns

Open up port in firewall::

	$ firewall-cmd --permanent --zone=public --add-service=http

	$ firewall-cmd --reload


Warning:

	May need: setenforce Permissive


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