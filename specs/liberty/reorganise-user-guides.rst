..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================================
Reorganise User Guides for Liberty
=====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/reorganise-user-guides

Update the information architecture of the End User Guide and Admin User
Guide to ensure that user and operator content is separated, and the existing
content is accurate and relevant.

Problem description
===================

The current user guides have become disorganised over time, this update
tidies them up.

Proposed change
===============

* Identify different types of content in the guides
* Reorganise guides to better present existing content
* Clean up existing content where necessary
* Identify information gaps and raise bugs where necessary
* Be sure that terms are well-defined here (or link to other docs
  for definitions)

Alternatives
------------

* Leave the guides as they are

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Lana Brindley (loquacity)

Other contributors:
  The User Guides specialty team
  Anyone with information architecture experience

Work Items
----------

* Develop a user/task matrix and define a limited set of personas to consume
  the user guide content.

* Remove the unnecessary/self explanatory procedures from the dashboard
  chapter, for example, 'Delete an image' or 'Manage an instance' and so on.

* Determine a good structure for how to present tasks, using the dashboard or
  CLI, and editing config files.

* Right now some procedures are included in both the guides with minor
  differences. Keep them in one guide (may be the user one) and remove from
  the other. May be somewhere in the beginning of the admin guide, we can
  add a paragraph saying this guide talks about the admin only procedures,
  but the admin can also perform all the procedures in the user guides or
  something similar.

Dependencies
============

* None

Testing
=======

* None

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [user guides]
  in the subject, weekly user guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/User_Guides

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting
