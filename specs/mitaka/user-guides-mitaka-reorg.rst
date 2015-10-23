..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
User Guides Reorganization for Mitaka
==========================================

Edit and modify the Cloud Administrator Guide with the
Admin User Guide, and the End User Guide to make sure the content supports
administrators, end users, and cloud administrators. Reorganization of
existing content needs to empower users, and grant administrators control.

Problem description
===================

The three guides have recieved edits, and are now in .rst format. The content
between the guides shows inconsistency, and existing content could be
reorganized to ensure consistency.

Relevance and accuracy of the current procedures and tasks also requires
attention. Reorganizing where information appears between the three guides
will help to further support for users and control for administrators.

Proposed change
===============

1. Handle inconsistency and improve accuracy by
   reporducing or moving some concepts described in the Cloud Administrator
   Guide into the Administrator and User Guide. In addition:

  * Clarify the audience of each guide, with a user task matrix and results
    from the OpenStack foundation administrator survey.
  * Find oppurtunities to reduce the number of files by combing sections.
  * Clean up existing content with grammer checks, use of definite articles,
    and verb subject agreement.
  * Address consistency of tables accross the guides - adjust to a
    variable list with bold headings, or a table with :code: roles inside
    the cells to illuminate commands.
  * Reorganize troubleshooting sections into a single format - Change the
    Troubleshooting sections to use a "Problem" and "Solution" format
    recruited in the Block Storage Chapter.

2. Potentially restructure Guides - Conditional roles in some OpenStack
   documents separate different set of tasks, and a similar structure
   could improve the Administrator and End user guide. Combining these
   guides together would have the benefit of reducing the number of
   files to track in the repository.

Alternatives
------------

1. Implement only The first proposed change, and keep three separate guides.

2. Combine the Cloud Administrator Guide with the Administrator Guide instead.

3. Do not implement these changes, and edit the guides on a smaller scale.

4. No changes.

Implementation
==============

Assignee(s)
-----------
Joseph Robinson(joseph-r-email)
Brian Moss(kallimachos)

Other Contributors
------------------
The User Guide Team, and anyone willing to test the Cloud Administrator and
Administrator Guide procedures for accuracy on test installations.

Work Items
----------

Work items are broken down by chapters from the Cloud Admin Guide.

Identity Management
~~~~~~~~~~~~~~~~~~~
* User CRUD: include information and a brief procedure on how
  to do this in the ADMIN USER Guide.
* Start the identity Service: Move this content into another section
  to reduce the number of files in the repository.
* External authentication with Identity: Another smaller section in the
  identity service that can merge.

Compute
~~~~~~~
* AMPQ: introductory colons to introduce a list, capitalising
  abbrieviations in brackets (AMPQ)
* Hypervisors: Reorganize and link to the Admin User Guide. Include a
  section on how to use a hypervisor.
* Tenants, users, roles: Remove passive voice. Link to the
  "How Can I Use The Cloud?" section of the End User Guide
  *Admin User Guide* - Create and manage roles - reorganize this content to
  align with the Cloud Admin Guide content.

EC2 compatibility
~~~~~~~~~~~~~~~~~
* Remove passive voice.

Building Blocks
~~~~~~~~~~~~~~~
* Introduction: Clarify what base operating system is referred to here.
  Check content for accuracy.
* The nova image-list command. Link together the content on the nova
  command line client with the *End User Guide* here.

Images and Instances
~~~~~~~~~~~~~~~~~~~~
* Align the introduction wiht the *End User Guide*.
* Align the Lanching instances and the Adding and removing resources
  section with the *Admin User Guide*.
* "This diagram shows the system state prior to launching an instances"
  Describe the parts of the diagram. The paragraph is not clear. Extend to
  the modifications to the other diagrams.

Networking with nova-network
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* The Cloud Admin Guide references floating IP addresses, which users can
  change. The User Guide section on Networking will need reorganization to
  line up with this content. Information on how to assign IP addresses to VM's
  also needs testing.
* VLAN Network Manager: Check paragraph intendation.
* nova network-create vmnet: Address table consinstency accross guides.
* Configure Compute to use IPv6 addresses: Address table consistency
  accross guides.

Metadata
~~~~~~~~
* Liberty to Mitaka-metadata services now include 'project_id' acording to
  release notes.
* Metadata needs an SME check for currancy. (Andrew Bogott, John Garbutt,
  Matthiew Gagne)
* Description of metadata config options table: Address table consistency
  accross guides.

Flavours
~~~~~~~~
* Flavours define these elements table: Address table consistency
  accross guides. (Bold headings with sentences here).
* Are the tables in the *Admin User Guide* on setting flavours effective?
* Show Host Useage Statistics: Host usage statistics description, and
  change to bold headings.

Secure with Rootwrap
~~~~~~~~~~~~~~~~~~~~
* Configuration option [Default]: SME to check, and change to better format.
  Might need a code snippet
* Migrate Instances: These tables were code nippets. Can they be
  replaced with images or appropriate code snippets?
* VNC configurations options: Include a descriptions of VNC configuration
  options
* Frequently Asked Questions: An FAQ in the guide clashes with the other
  information.
* Information Architecture checkup needed here to rework this information.
* Security Hardening: Improve the OpenStack with Trusted Compute Pools
  Second diagram. a new diagram needs headings, and consistency with
  the other diagrams.
* Recover Cloud After disaster: Test or have SME check on this procedure.

Object Storage
~~~~~~~~~~~~~~
* *User Guide*: The Create and manage object containers section needs content
  from the introduction to the Object Storage section of the 
  *Cloud Admin*. "...Object Storage (code-named swift is open source
  software for creating redundant, scalable data storage using clusters..."
* Object Storage Characteristics - Does not mention containers, but the *User
  Guide* mentions this term. Edit for Consistency.
* Components: Edit passive voice usage, and adjust the openening sentence
  introducing the components. Move the descriptive opening sentece to
  the introduction, and into the *Admin User Guide* section on Object Storage.
* Rings: Underneath the Ring diagram, edit these sentences for a comma splice.
* Zones: Mentions the high availabilty plus other components already mentioned
  in the Components section. So, Components description is not needed. Edit for
  Repetition.
* Partitions: Edit for punctuation - Comma Splice
* Change the Cluster Architecture and Ring Builder Sections within the Block
  storage chapter.
* Account Reaper: "In the background, the account reaper removes
  data from deleted accounts..." Edit the syntax here.
* Object Storage Monitoring - Excerpt from a blog. Keep or remove? This
  section also needs a syntax review.

Block Storage:
~~~~~~~~~~~~~~
* Block Storage: persistent storage needs to be mentioned earlier and more
  clearly in this introduction.
* Migrate volumes: These commands could appear in the *End User Guide*
* Block Storage command line list: "cinder-manager host lists",
  "cinder get-pools" Adapt for the *Admin User Guide*.
* Back up and Restore volumes: Is this procedure a cloud admin procedure, or
  can the basic information be adapted to the *Admin User Guide*? Requires role
  clarification.
* Clarify if the Transfer a volume section in the *Admin User Guide* is similar
  to the Export and import backup metadata procedure in the *Cloud Admin Guide*.
* Configure and use volume number weigher: This proceudre references cinder
  commands described in the *End User guide* and *Cloud Admin Guides*.
  Reorganize this content.
* Supported Operations in filter and goodness functions: Remove passive voice in
  the Caution note.
* Rate-limit volume copy Bandwitdth: Reorganize the guide such that this content
  appears closer to the information on moving and migrating block stoarge volumes
  ("volume_copy_bps_limit").
* Image volume cache: Remove passive voice.
* Get capabilities: This section describes actions an administrator can take
  with an API,
  capability investigation. Reorganize this information with the
  *Admin User Guide*.
* Multipath call failed exit: This Troubleshooting section recruits a
  Problem and Solution heading architecture.

Shared File System
~~~~~~~~~~~~~~~~~~
* Key Concepts: Remove passive voice.
* Share basic operations: " General concepts " edit or clarify this phrase.
* Manilla commands show, update, and delete options could appear in the
  *Admin User Guide*. Clarify Shared File System responsibilities.
* Manage and unmanage share: Edit missing words in some sentences
* Resize a share: Also missing words here.
* Quotas and Limits: Edit verb subject agreement.
* Share snapshots: Include the manila snapshot-create command listed in
  the *Admin User Guide* here.
* Consistency group: Edit verb subject aggreements ("admin to admins").
* Scheduling: Edit for article and definite articles.
* Networking - Edit for missing words.
* Share networks - Edit verb subject aggreements

Networking
~~~~~~~~~~
* Plug-in configurations section: Document the most common ml2 plug-in
  configurations.
* Reference nework option plugins for ml2
  http://docs.openstack.org/liberty/config-reference/
  content/networking-options-plugins-ml2.html.
  See https://bugs.launchpad.net/openstack-manuals/+bug/1411624
* Use Networking section: Networking Tables need consistency with the
  other *Cloud Admin Guide* tables.
* Networking Architecture: This sections description of archtecture
  would be better placed following the introduction.
* Configuring Identity for Networking: A note about not using Nova-network
  with compute appears here,
  but needs to appear earlier - the introduction - as a warning for cloud
  administrators.

Telemetry
~~~~~~~~~
* Data Retrieval: The code snippet tables need to fit the page.
* Measurements: Confirm that no other measurment items are added
  from the Liberty release.

Orchestration
~~~~~~~~~~~~~
* Orchestration Authorization Model: This section requires an edit for grammar.
* Stack domain users: Grammar Edits also required for this section.
* Cross-origin resourcs charing: The sub-section "enabling CORS with
  configuration" needs an edit to change into a procedure
  rather than a list of items.

Dependencies
============

* None

Testing
=======

* Some testing required for networking, and core services on Devstack
  environments, and OpenStack test installations.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [user guides]
  in the subject, weekly user guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and notes for any further work
  items can be recorded in the `User Guide Etherpad`.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/User_Guides

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`User Guide Etherpad`: https://etherpad.openstack.org/p/UserGuideSpecification
