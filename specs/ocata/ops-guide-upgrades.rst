..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

.. _ops-guide-upgrades:

=================================================
Operations Guide: Reference project upgrade notes
=================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/ops-guide-upgrades

Problem description
===================

Service upgrade notes located in project repositories require greater
visibility for operators.

Proposed change
===============

Several project teams have produced upgrade notes in the developer
documentation that are beneficial to operators:

- `keystone <http://docs.openstack.org/developer/keystone/upgrading.html>`_
- `nova <http://docs.openstack.org/developer/nova/upgrade.html>`_ ,
- `cinder <https://review.openstack.org/#/c/393395/>`, and
- `neutron <http://docs.openstack.org/developer/neutron/devref/upgrade.html>`_

Due to a short development cycle for Ocata, the interim solution is to
provide links to this information in the Operations Guide to improve
visibility for operators. Links to other service upgrade notes will be added as
they become available.

There is a growing need to provide a project-based upgrade guide. During Ocata
development cycle, this can be discussed further, and give the opportunity for
other core project teams to discuss and document upgrade strategies. Then
potentially scope and plan a guide at the OpenStack Project Technical Group
meeting for the Pike release.

Alternatives
------------

* Leave as is.

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

* Add links to keystone, nova, cinder, and neutron upgrade notes.

* Add links to other service upgrade notes when they become available.

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
