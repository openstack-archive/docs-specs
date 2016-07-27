..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===============================
User Guides Consistency Editing
===============================

Problem Description
===================

After the docs changes and rebuilds during the Mitaka release cycle,
several editing items that touched both the OpenStack Administrator
and OpenStack User Guide remained. This spec makes these
items a priority for Newton. It also introduces work items that have
been raised on the docs mailing list or in reported bugs.


Proposed Change
===============

Edit the tables and code snippets to ensure they appear consistent
across the OpenStack Administrator Guide and the OpenStack User Guide.

Use the information on Personae in the OpenStack Contributor Guide to
confirm that chapters in the Administrator Guide, and content appearing
within chapters, is informative for the audience. Link together certain
sections in the guides when appropriate: for example "For more information
on Migrating Volumes, see the OpenStack User Guide".

Make specific adjustments to the Information Architecture - where content
appears in specific chapters:

* Networking - Configuring Identity for Networking. Move the note earlier.
* Block Storage - persistent storage needs to appear earlier.
* Secure with Rootwrap - Move and rework the architecture of the FAQ section.

Plus, other sections as needed.

Include new diagrams for the security hardening content, specifically,
improve the OpenStack with Trusted Compute Pools Second diagram. A new
diagram needs headings and consistency with the other diagrams.

Replace the legacy client commands with up-to-date OpenStack CLI commands
in all examples in the User Guide.

Alternatives
------------

* Complete the proposed changes as individual bugs instead of a blueprint.

* Leave the guides as they are.

Implementation
==============

Assignee(s)
-----------

* Joseph Robinson
* Any Contributors associated with the User Guide, or interested in
  contributing to the User Guide Information Architecture.

Work items
----------

Chapters and edits proposed:

Administrator Guide

* Telemetry - adjust code snippets.
* Networking - Adjust tables in the Use Networking section.
* Secure with Rootwrap - tables here were code snippets. Restore them or
  adapt the content.
* Flavours - The tables in this section have bold headings. Adjust this
  design choice across the User Guides.
* Nova Networking - The table Configure Compute to use IPv6 addresses
  needs consistency across the User Guides.
* Block Storage - Migrate Volumes and Back up and Restore volumes need
  adjustments to their audience. Confirm they fit the audience, or adapt
  to fit into the User Guide. Connect nova-image list content to the
  User Guide. Move the persistent storage content earlier in the Back up
  and Restore volumes chapter. Move the Rate Limit content closer to the
  information on migrating Block Storage Volumes. Move the storage
  service quotas information.
* Networking - Rework Networking tables for consistency. Adjust
  placement of admonitions, and Networking Architecture information.
* Security - An improved security hardening for the Trusted Compute
  Pools section.

User Guide

* Adapt the legacy command line client content, updating the examples to
  use the more recent OpenStack command line client.

Dependencies
============

This spec is intended as a work item for the Newton release

Testing
=======

Ensure the document builds with new tables and diagrams

References
============

None.

