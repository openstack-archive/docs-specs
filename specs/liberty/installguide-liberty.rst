..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================================
OpenStack Liberty Installation Guide: Content Update
====================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/installguide-liberty

After the RST conversion, change the network architecture and update
configuration options as Liberty approaches usability.

Refer to the Installation Guide RST conversion spec for more information
about the RST conversion.

Refer to the Installation Guide for Debian spec for more information about
the Debian guide.


Problem description
===================

For the Liberty time frame, the following tasks need to be accomplished for
the Installation Guide:

* Architectural changes for network paths
* Configuration changes
* Testing


Proposed change
===============

After the RST conversion, change the architecture to remove nova-network path,
change existing neutron path to use the Linux bridge agent, add a neutron
path to implement provider networks with the Linux bridge agent, and update
configuration items using a combination of the configuration reference and
packages as they become available for Liberty. As time and resources permit,
implement optional enhancements TBD.


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

Architectural

* Remove nova-network path.
* Change neutron conventional (tenant/external) network path from Open vSwitch
  to Linux bridge agent.
* Add neutron provider network path with Linux bridge agent.

Configuration

* Update configuration items (TBD).


Dependencies
============

Liberty milestone or RC packages for each distribution supported by the
Installation Guide.


Testing
=======

* All distributions supported by the Installation Guide must complete
  `testing`_ of at least core services (Identity, Image Service, Compute,
  and Networking) and successfully launch an instance using both provider
  and conventional (tenant/external) network paths. Distributions that do
  not meet these criteria risk temporarily removal from publication.

.. _`testing`: https://wiki.openstack.org/wiki/LibertyDocTesting

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly Installation Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/InstallGuide

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`Liberty blueprint discussion`: https://etherpad.openstack.org/p/Documentation__Blueprint_Work_Session

