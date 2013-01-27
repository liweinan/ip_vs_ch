A consistent hashing scheduler for LVS
======================================

A consistent hashing scheduling module for <a href="http://www.linuxvirtualserver.org/">LVS(Linux Virtual Server)</a>

<a href="http://en.wikipedia.org/wiki/Consistent_hashing">Consistent hashing</a> is a better algorithm than mod, for the later might cause most of connections lose when the back-end servers is changed. 

In our case, we need to support stickiness for multiple directors in LVS, so the consistent-hashing solution is a nice choice to meet our requirement.

How to comipile:
----------------

a, install gcc kernel-headers kernel-devel(yum or apt-get)
b, make modules
c, make modules_install

How to check if ip_vs_ch is installed:
--------------------------------------

a, modprobe ip_vs_ch
b, lsmod | grep ip_vs_ch

Issues:
-------

a, if current kernel version is different kernel-devel:

   update kernel version or search kernel-devel match current version

References:
-----------
a, Consistent hashing library comes from <a href="http://www.codeproject.com/Articles/56138/Consistent-hashing">libconhash</a>

License:
--------
Under GUN License
