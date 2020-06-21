..  _sysadmin:

# documentation

$sys_admin
===========

Webmin Specific
---------------

- Create a webmin user password like so::

	$ /usr/libexec/webmin/changepass.pl /etc/webmin root YOURPASSWORD.

- Ubuntu specific::

	$ /usr/share/webmin/changepass.pl /etc/webmin root YOUR_PASSWORD

- Download with wget::

	$ wget http://prdownloads.sourceforge.net/webadmin/webmin-1.900-1.noarch.rpm

- Install needed dependencies::

	$ yum -y install perl perl-Net-SSLeay openssl perl-IO-Tty perl-Encode-Detect

- Install w/ RPM::

	$ rpm -U webmin-1.900-1.noarch.rpm

- If you are running a firewall and you should be, you will need to open up port 10000::

	$ sudo firewall-cmd --add-port=10000/tcp --permanent

	$ sudo firewall-cmd --reload

- Access the site here:

	https://localhost:10000