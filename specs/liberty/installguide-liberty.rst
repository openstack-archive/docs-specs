..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================================
OpenStack Liberty Installation Guide: RST Conversion
====================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/installguide-liberty

The OpenStack Installation Guide will be converted to RST.
DocBook will continue to be maintained in stable/kilo.


Problem description
===================

For the Liberty time frame, the following tasks need to be accomplished for
the Installation Guide:

* RST conversion
* Liberty installation updates and testing

This spec is primarily concerned with the RST conversion.


Proposed change
===============

Freeze development on the Installation Guide.

Convert Installation Guide to RST, concentrating on installation of core
services: nova, cinder, glance, keystone, neutron, swift.

Conditionals can be applied with the `ifconfig` extension:
.. _`ifconfig description`: http://sphinx-doc.org/ext/ifconfig.html

Conditional tags will be simplified as much as possible, grouping content
according to operating system group:
 * `ubuntu-based`
 * `fedora-based`
 * `opensuse-based`

Plan for Debian install guide may be addressed in a separate spec.

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

Freeze on updates in master.

Track changes in wiki:
.. _`wiki`: https://wiki.openstack.org/wiki/Documentation/Migrate

Update our build infrastructure so that Sphinx is used for publishing the
Installation Guide.

Once migrated, apply new openstackdocstheme template to the guide.

Dependencies
============

TBD

Testing
=======

We need to test the new HTML design on these browsers/operating systems
as a priority:

* Chrome on Ubuntu, Fedora, Mac, Windows
* Firefox on Ubuntu, Fedora, Mac, Windows

Need to test PDF output.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly Installation Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/InstallGuide

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`rst conversion discussion`: https://etherpad.openstack.org/p/Documentation__RST_Migration

.. _`Liberty blueprint discussion`: https://etherpad.openstack.org/p/Documentation__Blueprint_Work_Session

