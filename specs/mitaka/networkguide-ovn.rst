..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

============================================
Networking Guide: Open Virtual Network (OVN)
============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/networkguide-ovn

Add OVN content to the networking guide in coordination with the development
process.


Problem description
===================

OVN requires sufficient documentation that appeals to potential
deployers when or before it becomes part of an Open vSwitch release
during the Mitaka development cycle or after release.


Proposed change
===============

Develop the following OVN content:

* Introduction including comparison to existing virtual networking
  architectures.

* Architecture including components, control plane flow, data plane
  flow, etc.

* One or more realistic deployment scenarios including step-by-step
  instructions for networking service components.

* Optionally, migration from other architectures such as conventional
  Open vSwitch and agents.

All content may contain links to external documentation for general
information rather than duplicating it.

Alternatives
------------

Do not develop OVN documentation that appeals to potential deployers.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  ionosphere80

Other contributors:
  emagana
  russellb
  mestery

Work Items
----------

* Track development and review existing documentation in the following
  locations determine a plan for contributions.

  http://openvswitch.org/support/dist-docs/ovn-architecture.7.html

  http://blog.russellbryant.net/2015/10/22/openstack-security-groups-using-ovn-acls/

  https://github.com/openvswitch/ovs/blob/master/tutorial/OVN-Tutorial.md

  http://docs.openstack.org/developer/networking-ovn/

* As functions and features become stable, develop architectural content
  using a combination of existing and original content.

* As ability to deploy in a traditional multi-node environment becomes
  apparent, develop one or more realistic deployment scenarios. All
  scenarios require validation using an actual environment before
  publication.


Dependencies
============

* Sufficient progress in OVN development.

* Suitable environment for building and validating deployment scenarios.


Testing
=======

* Validate deployment scenarios.


References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, #openstack-neutron, #openstack-neutron-ovn, the
  openstack-docs mailing list, weekly `documentation team meeting`_,
  weekly `neutron team meeting`_, weekly OVN meeting on Thursdays
  at 13:15 US eastern time in #openvswitch, and potentially
  etherpads.

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`neutron team meeting`: https://wiki.openstack.org/wiki/Network/Meetings
