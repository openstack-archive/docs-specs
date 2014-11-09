..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=========================================
Move driver docs out of openstack-manuals
=========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/move-driver-docs

TBD

Problem description
===================

Many OpenStack projects include drivers to support specific hardware
or software.

Examples are:
* Cinder: block storage drivers
* Neutron: network plug-ins
* Nova: hypervisors
* Trove: Different databases



Proposed change
===============

The documentation team will only document the default drivers as
specified below and just add links for other drivers.

Guidelines for drivers that will be documented in the openstack
documentation:

* The driver must be fully open source
* The driver must be part of the respective OpenStack repository
* The driver is considered one of the default drivers

For documentation of other drivers, the following guidelines apply:

* The Configuration Reference will contain only a single link to an
  external document
* Only drivers are linked that are contained in the official OpenStack
  project repository for drivers (for example in the main project
  repository or the official "third party" repository).

With this policy, the docs team will document in their guides the
following:

* For cinder: document LVM only
* For glance: Document local storage and using cinder as backend
* For neutron: document ML2 plug-in with the mechanisms drivers
  OpenVSwitch and LinuxBridge
* For nova: document KVM (mostly), send Xen open source call for help
* For sahara: apache hadoop
* For trove: mysql/mariadb

Alternatives
------------

* Keep status quo: Add all drivers to Configuration Reference

Implementation
==============

Assignee(s)
-----------

jaegerandi

Work Items
----------


Dependencies
============

* Inform third party driver contacts about change

* Remove all files

* Add back links for external websites


Testing
=======


References
==========

https://etherpad.openstack.org/p/docstopicsparissummit
