..  _nginx:

# documentation

$nginx
===========

Basic Setup
-----------

- CentOS specific::

	$ load epel 

	$ sudo yum install epel-release

	$ load nginx

	$sudo yum install nginx

	$ sudo systemctl enable nginx


- Open up port in firewall::

	$ firewall-cmd --permanent --zone=public --add-service=http

	$ firewall-cmd --reload

