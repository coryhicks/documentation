$networking
========

basic tasks
--------

- disable ipv6::

	$ sudo sysctl -w net.ipv6.conf.eth0.disable_ipv6=1

- add to /etc/sysctl.conf::

	$ net.ipv6.conf.eno0.disable_ipv6=1

Firewall
------------

- firewall to allow dns qrys

    $ sudo firewall-cmd --zone= --add-service=dns

