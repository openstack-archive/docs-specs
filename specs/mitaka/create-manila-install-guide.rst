..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Add manila to the installation guide
====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/create-manila-install-guide

Add manila to the installation guide.

Problem description
===================

The installation guide does not include manila, but manila packages are
available in the distros' repositories. Essential documents also
already support manila:
- `Manila admin guide cloud http://docs.openstack.org/admin-guide-cloud/shared_file_systems.html`__
- `Manila user guide <http://docs.openstack.org/user-guide/cli_manage_shares.html>`__
- `Manila configuration reference <http://docs.openstack.org/liberty/config-reference/content/ch_configuring-openstack-shared-file-systems.html>`__

Proposed change
===============

Add manila to the installation guide using existing cinder content as a
reference.

Manila architecture is based on cinder architecture. By this means, reference
architecture will be compatible with cinder architecture.

Approach for example/proof-of-concept architecture:
- Shared Filesystems Storage management at the controller node;
- Shared Filesystems Storage service at same the cinder node.

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  denis-cavalcante

Work Items
----------

None

Dependencies
============

Mitaka milestone or RC packages for each distribution supported by the
Installation Guide.

Testing
=======

Validate manila deployment on all distributions supported by the installation
guide.

References
==========

None
