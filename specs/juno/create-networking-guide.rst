..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

================
Networking Guide
================

https://blueprints.launchpad.net/openstack-manuals/+spec/create-networking-guide


Problem description
===================

Since the Havana release, OpenStack has not had a single guide devoted to
understanding and deploying OpenStack Networking. There is some information
in other guides, particularly the Cloud Administrators Guide, but no single
guide that discusses different networking scenarios and solutions.

Proposed change
===============

We should create a Networking Guide, following roughly the outline here:

https://wiki.openstack.org/wiki/NetworkingGuide/TOC

The target audience for this information is cloud administrators who
have experience with OpenStack administration and general system
administration, but who may not be especially knowledgeable about
networking concepts.

This document is targeted for the Juno release.

The base architecture uses three nodes: a controller and compute nodes
as set up in the Install Guide, plus a network node to run Neutron
agents. This is the same architecture used in the Cloud Administrators
Guide:

http://docs.openstack.org/admin-guide-cloud/content/network-connectivity.html

It will use the same conventions for naming and services as the Install
Guide, many of which are covered on the wiki:

https://wiki.openstack.org/wiki/Documentation/Guide_conventions

Network types to be covered:
* Local
* VLAN
* GRE
* VXLAN

Mechanisms to be covered:
* Linux Bridge
* OVS
* Open Daylight
* L2 Population
* Proprietary (depending on time constraints)

All instructions are to use the ML2 plug-in.

Timeline and Events:
* docs swarm (2014-08-09)
* ops meetup (upcoming)
* bug squash day (upcoming)

Alternatives
------------

* Adding more information on networking to guides such as the Cloud
  Administrators Guide, Operators Guide, and Install Guide. These
  documents already contain some networking information. However,
  for them to cover the full breadth of what's proposed could add
  significant bulk to each.

Implementation
==============

The Networking Guide will live alongside other guides in the
openstack-manuals repository. There is already some stub content.

Assignee(s)
-----------

Primary assignee:
  shaunm-gnome

Other contributors:
  nickchase
  phil-hopkins-a
  ionosphere80
  emagana
  loquacity


Work Items
----------

* Stub out outline of sections and information to be included.
* Determine whether content already exists, and whether it can be included
  or whether it needs to be copied in and edited.
* Have multiple contributors write sections with help from SMEs.
* Review contributions, prioritize content, and possibly prune for release.


Dependencies
============

Need reviewers from Neutron

Testing
=======

* Have SMEs review all conceptual information for accuracy.
* Manually test all instructions to ensure they work.

References
==========

None
