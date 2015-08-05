..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============
OpenStack Labs
==============

https://blueprints.launchpad.net/openstack-manuals/+spec/openstack-labs

OpenStack Labs will provide automated way of deploying a multi node
OpenStack cluster on a lean basis. OpenStack Labs should provide a
easy way to setup OpenStack cluster which should be a good starting
point for beginners to learn OpenStack, and for advanced users to
test out new features, check out different capabilities of OpenStack.
On top of that OpenStack Labs will also be a good way to test the
install guides on a regular basis.

Problem description
===================

Deploying OpenStack could be really challenging for beginners. OpenStack
Labs would provide a simple automated way to have a multi-node vanilla
OpenStack deployment on virtual machines. The following are the unique
traits:

* Easy to setup and run.
* Minimal dependencies.
* Minimal hardware requirements:

  * 4GB RAM
  * i3 processor (or similar quad core processor)
  * 50GB hard disk space.

* Supports multiple platforms:

  * Linux
  * Mac
  * Windows

* Closely follows install-guides.

Proposed change
===============

* The work will be carried out by OpenStack Labs, speciality team.
* Creation of new repository.
* Migrating labs folder under training-guides to the new repository:

  * Setup a new github repository for migration.
    using git-filter on the labs section of training guides.
  * Propose a new repository in OpenStack and import content from
    github repository.

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* dguitarbite

Other contributors:

* rluethi
* sayalilunkad

Work Items
----------

* Migrate labs folder from training-guides to the new repository location:

  * Using git-filter get the labs specific content from training-guides
    repository.
  * Move it to a github repository.

* Create openstack-labs repository, pull the content from the github
  repository.
* Refactor the repository structure to include new architecture.

Dependencies
============

* T.B.D.

Testing
=======

* Add bash and python syntax checks.
* Create required infra jobs for openstack-labs.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly Installation Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/OpenStack-Labs

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

