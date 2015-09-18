..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================================================
Add Shared File Systems (Manila) to the Config Reference
========================================================

Launchpad blueprint:

https://blueprints.launchpad.net/openstack-manuals/+spec/manila-config-ref

Shared File Systems (Manila) should be added to the Config Ref similar to
Block Storage (Cinder).


Problem description
===================

Shared File Systems (Manila) is not currently included in the
Configuration Reference. The Manila documentation is currently
kept in-tree in the Manila devref. Administrators using Cinder, Swift
and Manila would expect to find a similar reference for all three
projects in the Configuration Reference. The automated configuration
doc tools should be leveraged.


Proposed change
===============

The content would be similar to Cinder in that it would have sections
to describe Intro, Drivers, Log Files and Options. The Drivers section,
however, would use shorter more stable descriptions of drivers and use
links to vendor web sites and in-tree vendor docs.

Automatically generated configuration tables should be used where
possible.


Alternatives
------------

The amount of vendor driver documentation that should be included
in the Configuration Reference if up for discussion. The current
direction suggests using links to other docs for things that change
from release to release. For Manila, we could use links to the
existing devref. The devref is easy for developers to maintain
in-tree. So, that is good for technical details. Unfortunately the
reading experience will suffer if we don't keep "the right amount"
of information in the Configuration Reference. So we'll need to
work on finding that right amount.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Mark Sturdevant (mark-sturdevant)

Other contributors:
  Existing vendor docs from Manila in-tree devref.

Work Items
----------

* shared-file-systems chapter
* Generated configuration file tables


Dependencies
============

* Manila is near RC1, so functionality is frozen.

* Manila devref documentation for Liberty is not final. Some vendors
  should be improving their documentation while this is in progress.
  Some pages may need a re-sync once we get a base Config Ref -- or we
  could use separate commits for each vendor to try to capture
  all their Liberty updates in each first commit.


Testing
=======

Review by the Manila core team and contributors.

References
==========

Manila devref:

* http://docs.openstack.org/developer/manila/devref/index.html
