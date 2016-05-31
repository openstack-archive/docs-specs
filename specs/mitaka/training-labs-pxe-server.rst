..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Trainig-labs PXE server
==========================================

Include the URL of your launchpad blueprint:

https://blueprints.launchpad.net/openstack-manuals/+spec/pxe-server-osbash

Training-labs can currently install OpenStack into local virtual machines.
But what happens if we want to build a test environment on an unsupported
virtual environment, or even in physical machines?

Provided that osbash already builds the framework to install a Virtual
Machine (VM), we can install on it a PXE (Preboot eXecution Environment)
server, which will provision Ubuntu into a given network.
Setting this VM with bridged networking can allow to just plug our laptop
into a network switch, and install OpenStack "the osbash way" on real
 hardware.


Proposed change
===============

Create a new install option called ``pxeserver`` with the following workflow:

* Create the Base disk as usual

* Clone the Base disk and set the network card for bridged networking

* Install/configure the required services:
  This includes: dhcpd, apache and tftpd
  Also, in order not to interfere with the default management/ext networks,
  there is a dedicated router and dns server, which will route the traffic
  from the external network into the PXE network. This provides internet
  access to the machines, for downloading packages.

* The kickstart file will provision an Ubuntu image with a custom menu,
  similar to the one in BOMSI, from where one can chose which machine is
  going to be installed (i.e. controller or compute)

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* Julen Larrucea (julenl)

Other contributors:

* Pranav Salunke (dguitarbite)
* Roger Luethi (rluethi)

Work Items
----------

* The kickstart file needs some hacking. This file is not the default one used
 by osbash, since i.e. the machine needs "real" networking from the very
 beginning

* The bridge network needs to be set on VirtualBox (or KVM)

* Decide whether the install scripts on the target (OpenStack) machines
 (controller/compute) are going to be executed via ssh or upstart scripts
 after reboot

* Set some MAC rules on the dhcp server, to avoid having to chose the
  machine to be installed, and enable full automation of the process

Testing
=======

Run:
./osbash.sh -b pxeserver

The machine will be accessible in subnet of the bridged interface with the
last octet being ``100``. If we are using the default networks, this could
be ``10.0.0.100``. The login credentials are the default ones for osbash.

References
==========

* The boot menu for the PXE provision is similar to the one in BOMSI:
  https://github.com/julenl/BOMSI/tree/master/Ubuntu-Liberty

