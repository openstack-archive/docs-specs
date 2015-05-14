..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
OpenStack Liberty Installation Guide
====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/TBD

Implement mandatory changes and optional enhancements to the Installation
Guide for Liberty.


Problem description
===================

The installation guide needs to be updated to work on OpenStack Liberty.

Conversion to RST may be discussed, but is not expected at this time.


Proposed change
===============

* Add changes required to make the guide compatible with Liberty
* Optional enhancements to the guide as time and resources permit

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  <launchpad-id or None>

Other contributors:
  <launchpad-id or None>

Work Items
----------

* RST conversion
   * Placeholder
      -Placeholder

* Mandatory changes
   * Placeholder
      - Placeholder



Dependencies
============

* Liberty milestone or RC packages for each distribution supported by the
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
