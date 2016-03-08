..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Add magnum to the installation guide
====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/magnum-installation-guide

Add magnum to the installation guide.

Problem description
===================

The installation guide does not include magnum. Other documents also already
support magnum:
- `Magnum command-line reference <http://docs.openstack.org/cli-reference/magnum.html>`__

Proposed change
===============

Add magnum to the installation guide using existing glance content as a
reference.

Magnum-conductor and Magnum-api reside on the controller node similar to
glance-registry and glace-api.

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  strigazi

Work Items
----------

None

Dependencies
============

Mitaka milestone or RC packages for each distribution supported by the
Installation Guide.

Testing
=======

Validate magnum deployment on all distributions supported by the installation
guide.

References
==========

None
