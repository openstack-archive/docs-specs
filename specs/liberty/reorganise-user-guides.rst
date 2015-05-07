..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================================
Reorganize User Guides for Liberty
=====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/reorganise-user-guides

Update the information architecture of the Cloud Administrator Guide,
Admin User Guide, and End User Guide to separate user, administrator,
and operator content, and ensure that the existing content is accurate
and relevant.

Problem description
===================

The current user guides have become disorganized over time, this update
tidies them up.

Proposed change
===============

* Clarify the audience of each guide
* Identify different types of content in the guides
* Reorganize guides to better present existing content
* Clean up existing content where necessary
* Identify information gaps and raise bugs where necessary
* Be sure that terms are well-defined here (or link to other docs
  for definitions)

Alternatives
------------

* Leave the guides as they are
* Combine the Cloud Admin Guide and the Admin User Guide
* Combine the Admin User Guide and the End User Guide

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

* Develop a user/task matrix and define a limited set of personae to consume
  the user guide content.

* Rework the abstract for each guide to clearly identify the audience and
  purpose of each book

* Remove the unnecessary/self explanatory procedures from the dashboard
  chapter, for example, 'Delete an image' or 'Manage an instance' and so on.

* Determine a good structure for how to present tasks, using the dashboard or
  CLI, and editing config files.

* Reduce duplication between the guides as much as possible. Point the Cloud
  Admin Guide to the Admin User Guide, and the Admin User Guide to the End
  User Guide for readers to accomplish further tasks. This information may
  be suited to the Abstracts.

* Update dashboard images for Admin and Project tabs.

* Verify if the procedures are applicable by testing against the Liberty
  puddle.

* Consistency with procedures: some have tables, some use variable
  list, for example:

  * Create Network (normal variable list)
  * Launch Instance (variable list in bold)
  * Manage stacks and Access & Security (tables)
  * Manage objects (bullets)

* Spacing between steps in procedures is inconsistent, for example, check
  "Procedure To copy an object from one container to another" and
  "Procedure: To create a metadata-only object without a file" in the
  "Manage an object" section of User guide.

* Some of the topics are repeated in TOC, for example:
  In the User guide, Log in to the dashboard in the OpenStack Dashboard
  chapter and from Overview to Manage volumes in the OpenStack command-line
  clients chapter. [http://docs.openstack.org/user-guide]
  Similarly, some of the sections are repeated in the admin user guide.
  [http://docs.openstack.org/user-guide-admin]

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
