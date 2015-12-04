..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

======================================
Networking Guide: Implement Versioning
======================================

https://blueprints.launchpad.net/openstack-manuals/+spec/networkguide-versioning

Implement versioning of the networking guide including publishing a stable
version for each OpenStack release similar to the installation guide.


Problem description
===================

The networking guide currently uses a continuous deployment mechanism
for publication. In other words, only the master branch resides on
docs.openstack.org. Several releases after initial publication of the
networking guide, the following issues with continuous deployment
became apparent:

* Using wording such as "In Kilo..." or "In Liberty..." is confusing and
  often difficult to find if a search leads to a specific page within the
  content for a particular feature available in a certain release of
  OpenStack. For example, a chapter has a note indicating that the
  Liberty release includes a particular feature, but sections within the
  chapter lack a note about it.

* Maintaining the deployment scenarios is difficult because features and
  configuration options change with each release. For example, DVR in Juno
  only supports GRE and VXLAN networks, but DVR in Kilo and newer releases
  also supports VLAN networks. Trying to use "In Kilo..." or "In Liberty..."
  in configuration snippets makes them increasingly confusing.


Proposed change
===============

Publish stable releases of the networking guide using the same schedule as
OpenStack releases. With the exception of bug fixes, patches apply to the
master branch and require additional consideration for backporting to
prior releases.

Stable release tags already exist for the networking guide. However, updates
to the networking guide for a particular release usually occur after that
release. For example, patches for the deployment scenarios in Kilo mostly
merged several months after the Kilo release. Therefore, the existing
stable/kilo tag primarily includes content that applies to Juno and the
stable/liberty tag primarily includes content that applies to Kilo. Aligning
content for prior releases requires careful backporting of a significant
quantity of patches.

After implementation of this specification, updates for a future release
should occur prior to that release similar to the installation guide.

Alternatives
------------

Retain continuous deployment for the networking guide.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  scollins

Other contributors:
  jaegerandi
  ionosphere80
  emagana

Work Items
----------

Phase 1

* Build networking guide for the stable/kilo branch and backport patches
  that apply to it.

* Publish the master branch to drafts and Liberty documentation.

* Publish the stable/kilo branch to Kilo documentation.

* Update redirects and index files as necessary.

Phase 2

* Update the networking guide (primarily deployment scenarios) for Liberty
  using the master branch.

* Build networking guide for the stable/liberty branch and backport
  patches that apply to it.

* Publish the stable/liberty branch to Liberty documentation.

* Update redirects and index files as necessary.


Dependencies
============

None.


Testing
=======

* Verify correct publication prior to moving to the next phase and
  ultimately implementing the specification.


References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, openstack-docs mailing list, weekly
  `documentation team meeting`_, bi-weekly
  `networking guide sub-team meeting`_, and potentially etherpads.

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`networking guide sub-team meeting`: https://wiki.openstack.org/wiki/Documentation/NetworkingGuide
