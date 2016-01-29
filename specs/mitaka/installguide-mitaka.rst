..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============================================
Installation Guide: General changes for Mitaka
==============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/installguide-mitaka

Discuss and track general changes to content for existing services in the
Mitaka release.


Problem description
===================

Prior to the Mitaka release, accomplish the following tasks for the
Installation Guide:

* Changes to existing distributions
* Changes to existing OpenStack service or system dependencies
* Addition of new distributions (requires separate spec)
* Addition of new services (requires separate spec)
* Complete testing on all distributions


Proposed change
===============

#. Update content using a combination of the configuration reference and
   distribution packages as they become available for Mitaka.
#. Remove defunct Debian content due to persistent lack of maintenance over
   many releases.
#. As time and resources permit, implement optional enhancements TBD.


Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  berendt

Other contributors:
  ionosphere80
  dguitarbite

Work items
----------

Architectural

* None unless OpenStack services dictate it.

Configuration

* Update configuration items (TBD).

Testing

* Perform sufficient `testing`_ on all distributions and track progress.


Dependencies
============

Mitaka milestone or RC packages for each distribution supported by the
Installation Guide.


Testing
=======

* All distributions supported by the Installation Guide must complete
  `testing`_ of at least core services (Identity, Image Service, Compute,
  and Networking) and successfully launch an instance using both provider
  and conventional (tenant/external) network paths prior to release of
  Mitaka. Additional services such as Block Storage and Object Storage
  also require sufficient testing, but can wait until the documentation
  team tags the official stable/mitaka release due to additional resource
  requirements. The documentation team may decide to temporarily disable
  publication of the installation guide for distributions that do not meet
  these criteria.

.. _`testing`: https://wiki.openstack.org/wiki/MitakaDocTesting

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly Installation Guide `specialty team meeting`_,
  and weekly `documentation team meeting`_. Also recommend using the
  `etherpad`_ to discuss potential changes before writing patches.

.. _`specialty team meeting`: https://etherpad.openstack.org/p/docinstallteam-agenda

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`etherpad`: https://etherpad.openstack.org/p/installguide-mitaka
