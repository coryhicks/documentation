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

- disable ipv6::

	$ sudo sysctl -w net.ipv6.conf.eth0.disable_ipv6=1

- add to /etc/sysctl.conf::

	$ net.ipv6.conf.eno0.disable_ipv6=1


Installation
------------

Install $project by running:

    install project

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