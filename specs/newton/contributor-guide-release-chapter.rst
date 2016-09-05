..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================================
Add release chapter to Contributor Guide
========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/release-chapter-contrib-guide

Information about how to conduct a documentation release is currently
contained in a wiki page, an etherpad, and several peoples' heads. In order
to make this content more accessible, to allow more people to be involved
in documentation releases, and to create a pipeline of people who understand
how to do a release, this should be documented in the Contributor Guide.

Problem description
===================

Current information about release procedures for documentation is contained
in a wiki page, several etherpads (see References), and other knowledge
is shared between a small number of people who have hands-on experience
with releases. This could potentially lead to data loss if the wiki is
decommissioned, or if etherpad has an outage. It also can lead to problems
if any of the subject matter experts are not available for consultation
during the release period.

Proposed change
===============

Add a new chapter to the Contributors Guide to consolidate the information
from the wiki, the etherpad, and the institutional knowledge.

Alternatives
------------

Do nothing: keep the information in its current locations, and hope no one
gets hit by a bus.

Implementation
==============

Assignee(s)
-----------

* Lana Brindley (Docs PTL)
* Andreas Jaeger (Docs Infra)
* Anne Gentle (Past Docs PTL)
* Past and present release managers

Work Items
----------

* Create new chapter in Contributor Guide (Lana)
* Add information from the wiki to the new chapter
* Add information from the past etherpad to the new chapter
* Add information from the current etherpad to the new chapter
* Have SMEs review and update content
* Review chapter after each release

Dependencies
============

None.

Testing
=======

None.

References
==========

* http://docs.openstack.org/contributor-guide/
* https://wiki.openstack.org/wiki/Documentation/Release
* https://etherpad.openstack.org/p/MitakaRelease
* https://etherpad.openstack.org/p/NewtonRelease
