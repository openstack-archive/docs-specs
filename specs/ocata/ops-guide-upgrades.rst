..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

.. _ops-guide-upgrades:

===========================================
Operations Guide: Add project upgrade notes
===========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/ops-guide-upgrades

Problem description
===================

The Operations Guide requires additional information about upgrading individual
OpenStack services.

Proposed change
===============

Several project teams have produced upgrade notes in the developer
documentation that are beneficial to operators:

- `keystone <http://docs.openstack.org/developer/keystone/upgrading.html>`_
- `nova <http://docs.openstack.org/developer/nova/upgrade.html>`_ ,
- `cinder <https://review.openstack.org/#/c/393395/>`, and
- `neutron <http://docs.openstack.org/developer/neutron/devref/upgrade.html>`_

The proposal is to migrate this information to the Operations Guide, along with
swift and glance upgrade notes when they become available.

The proposed structure for the Upgrades chapter in the Operations Guide
would be as follows:

- Pre-upgrade considerations
  - Upgrade planning
  - Pre-upgrade testing environment
  - Upgrade levels

- General upgrade process
  - Prerequisites
  - Perform a backup
  - Manage repositories
  - Upgrade packages on each node
  - Update services
  - Final steps

- Upgrade a service
  - Upgrade the Networking service
  - Upgrade the Identity service
  - Upgrade the Compute service
  - Upgrade the Block Storage service
  - Upgrade the Object Storage service

- Roll back a failed upgrade
  - Roll back an OpenStack environment
  - Roll back the Identity service
  - Roll back the Compute service
  - Roll back the Block Storage service
  - Roll back the Object Storage service

Alternatives
------------

* Leave as is.
* Provide links to the developer documentation in the Operations Guide.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* dazzachan

Other contributors:

* shilla-saebi
* alexandra-settle


Work items
----------

* Migrate keystone, nova, cinder, and neutron upgrade notes.

* Add swift and glance upgrade notes when they become available.

* Update or remove outdated information in the Upgrades chapter.

* Liaise with SMEs to review content.

Dependencies
============

* Swift and glance project teams providing upgrade notes during the Ocata
  development cycle.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [ops-guide]
  in the subject, monthly Ops Guide `specialty team meeting`_,
  biweekly `documentation team meeting`_.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/OpsGuide

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting
