..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================================
OpenStack Labs
====================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/openstack-labs

The OpenStack Labs speciality team aims to provide automated installation
of OpenStack on VirtualBox and KVM.


Problem description
===================

Deploying OpenStack can be really challenging for beginners. OpenStack Labs
provides a simple automated way to have a multi-node vanilla OpenStack
deployment on virtual machines. The following are the unique traits:

* Easy to set up and run.
* Minimal or no dependencies.
* Minimal hardware requirements.

  * 4GB RAM
  * i3 processor (or similar quad core processor)
  * 50 GB hard disk space

* Supports multiple platforms.

  * Linux
  * Mac
  * Windows

* Closely follows install-guides.



Proposed change
===============

* Add OpenStack Labs as a speciality team under Documentation Project.
* Create new repository.
* Migrate labs folder under training-guides to the new repository.

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

* Create openstack-labs repository.
* Migrate labs folder from training-guides to the new repository location.

  * Remove labs specific content from training-guides repository.

* Refactor the repository structure to include new architecture for adding
  Python support.


Dependencies
============

* T.B.D.

Testing
=======

* Add bash and Python syntax checks.
* Create required infra jobs for openstack-labs.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly Installation Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/OpenStack-Labs

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

