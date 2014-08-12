..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

================
Networking Guide
================

https://blueprints.launchpad.net/openstack-manuals/+spec/networking-guide


Problem description
===================

Since the Havana release, OpenStack has not had a single guide devoted to understanding
and deploying OpenStack Networking. There is some information in other guides, particularly
the Cloud Administrators Guide, but no single guide that discusses different networking
scenarios and solutions.

The target audience for this information is administrators who have experience with
OpenStack administration and general system administration, but who may not be especially
knowledgeable about networking concepts.

Proposed change
===============

We should create a Networking Guide, following roughly the outline here:

https://wiki.openstack.org/wiki/NetworkingGuide/TOC


Alternatives
------------

* Adding more information on networking to guides such as the Cloud Administrators
  Guide, Operators Guide, and Install Guide. These documents already contain some
  networking information. However, for them to cover the full breadth of what's
  proposed could add significant bulk to each.

Implementation
==============

The Networking Guide will live alongside other guides in the openstack-manuals
repository. There is already some stub content.

Assignee(s)
-----------

Primary assignee:
  shaunm-gnome

Other contributors:
  None

Work Items
----------

* Stub out outline of sections and information to be included.
* Have multiple contributors write sections with help from SMEs.
* Review contributions, prioritize content, and possibly prune for release.


Dependencies
============

None

Testing
=======

None

References
==========

None
