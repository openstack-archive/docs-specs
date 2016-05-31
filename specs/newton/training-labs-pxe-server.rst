..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=======================
Trainig-labs PXE server
=======================

URL of the launchpad blueprint:

https://blueprints.launchpad.net/openstack-manuals/+spec/pxe-server-osbash

Training-labs traditionally installs OpenStack on Virtual Machines on the
local machine. This feature should allow training-labs to provide PXE boot
functionality for installing the OpenStack cluster on bare-metal.

Training-labs at present builds the framework to install a Virtual Machine
(VM). Adding Preboot eXecution Environment (PXE) server as a VM in the
cluster should provide the bare-metal machines (physical hardware) or
optionally even Virtual Machines with the supported linux distributions
for installing and running OpenStack on top of it.

Setting this VM with bridged networking would allow us to make this PXE
server easily accessible from the physical machine (laptop/desktop/server/
VM/etc.) and install the OpenStack cluster using the existing deployment
solution and policies of training-labs on real hardware.

Proposed change
===============

To enable PXE boot feature the following changes would be necessary:

  * Adding PXE Server node to osbash.
  * Changing osbash CLI to add ``pxeserver`` option.
  * Installation and configuration scripts for PXE server.

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

  * Add new scripts which would allow PXE boot scenarios in training-labs.
  * Selecting the right way for automated installation of the operating
    system.
  * Creating appropriate policies for identifying the given role of a server.
  * Adding bridge network to the existing cluster.

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
