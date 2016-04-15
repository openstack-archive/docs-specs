..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Add trove to the installation guide
====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/create-trove-install-guide

Add trove to the installation guide.

Problem description
===================

The installation guide does not include trove, but trove packages are
available in the distros' repositories. Essential documents also
already support trove:

- `trove admin guide cloud <http://docs.openstack.org/admin-guide-cloud/database.html>`__
- `trove user guide cmd line <http://docs.openstack.org/user-guide/trove-manage-db.html>`__
- `trove user guide dashboard <http://docs.openstack.org/user-guide/dashboard_databases.html>`__
- `trove configuration reference <http://docs.openstack.org/liberty/config-reference/content/ch_configuring-trove.html>`__
- `trove API reference <http://developer.openstack.org/api-ref-database-v1.html>`__

Proposed change
===============

Add the following trove content to the installation guide:

**Prerequisites:**

Working OpenStack environment with at least Compute, Image Service, Identity.

- Backup and restore, add Object Storage.
- Provision datastores on block-storage volumes, add Block Storage.

**Installation:**

Install required packages.

Source ``admin-openrc.sh`` and create trove user.

Set OpenStack service URLs and RabbitMQ
values in ``trove.conf``,
``trove-taskmanager.conf``,
and ``trove-conductor.conf``.

Set correct ``api-paste.ini`` file values for ``auth_uri``,
``identity_uri``, ``admin_user``, ``admin_password``,
``admin_tenant_name``, ``signing_dir``.

Edit ``trove.conf`` for default datastore, network label, regex,
and API information.

Edit ``trove-taskmanager.conf`` to connect to the OpenStack Compute service.

Prepare the trove admin database.

Initialize database and create datastore.

Create a trove image.

Update the datastore to use the new image.

Register trove with keystone.

To deal with Ubuntu package bug - change the service startup scripts to use
the correct conf files.

Start or restart (depending on env) trove services.


Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Laurel Michaels

Work Items
----------

None

Dependencies
============

Mitaka milestone or RC packages for each distribution supported by the
Installation Guide.

Testing
=======

Validate trove deployment on all distributions supported by the installation
guide.

References
==========

None
