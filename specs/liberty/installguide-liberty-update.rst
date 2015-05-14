..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================================
OpenStack Liberty Installation Guide: Content Update
====================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/installguide-liberty

When RST conversion is complete and when Liberty information becomes
available, the OpenStack Installation Guide will be updated to
Liberty.


Problem description
===================

For the Liberty time frame, the following tasks need to be accomplished for
the installation guide:

* Liberty installation updates and testing


Proposed change
===============

When the RST conversion is complete and when information is available, add
changes required to make the guide compatible with Liberty

Optional enhancements to the guide as time and resources permit


Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  karin-levenstein

Other contributors:
  berendt
  dguitarbite
  jaegerandi
  ionosphere80

Work Items
----------

Add Liberty updates
* TBD


Dependencies
============

Liberty milestone or RC packages for each distribution supported by the
installation guide.


Testing
=======

* All distributions supported by the installation guide must complete
  `testing`_ of at least core services (Identity, Image Service, Compute,
  and Networking) and successfully launch an instance using both legacy
  networking (nova-network) and Networking (neutron). Distributions that
  do not meet these criteria risk temporary removal from publication.

.. _`testing`: https://wiki.openstack.org/wiki/KiloDocTesting

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly installation guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/InstallGuide

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`Liberty blueprint discussion`: https://etherpad.openstack.org/p/Documentation__Blueprint_Work_Session

