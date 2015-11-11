..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========
Upgrades
========

https://blueprints.launchpad.net/openstack-manuals/+spec/upgrades

Improve upgrade content by replacing rigid step-by-step procedures that
involve the installation guide architecture and upstream distribution
packages with more general procedures that appeal to a wider audience.


Problem description
===================

The existing upgrade content in the Operations Guide includes rigid
step-by-step procedures that rely on the simple installation guide
architecture and upstream distribution packages. Our audience of
operators deploy OpenStack in a variety of ways and would benefit
from more generic procedures that apply more easily to different
environments.


Proposed change
===============

Develop the following content for each service:

* Outline of the typical process including common issues. For example, address
  mandatory operational or configuration changes, stop the service, upgrade
  the code, upgrade the database schema, start the service, verify operation
  of the service.
* Mandatory or significant operational or configuration changes between
  releases.
* Links to release notes and configuration reference for other changes.

Mandatory or significant operational or configuration changes between
releases only consider upgrades from N-1 to N release back to the most
recent EOL release. Given time constraints, development prioritizes
upgrades between more recent releases.


Alternatives
------------

Continue using the existing content, likely without updates for recent
releases.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  none

Other contributors:
  none

Work Items
----------

* Develop a generic upgrade procedure.
* Determine mandatory or significant operational or configuration changes
  between releases and test upgrades using these changes.


Dependencies
============

* Suitable environment for deploying various releases and performing
  upgrades.


Testing
=======

* Verify generic upgrade procedure and augmentation with mandatory or
  significant operational or configuration changes for each release.


References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list, weekly
  `documentation team meeting`_, and potentially etherpads.

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting
