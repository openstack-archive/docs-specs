..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
User Guides Reorganization for Mitaka
==========================================

Edit Cloud Administrator Guide, Admin User Guide, and the End User Guide
to ensure the content supports administrators, end users, and cloud
administrators.

Problem description
===================

Having converted these guides to RST during the Liberty cycle, we can now
reorganize their content to improve consistency and reduce duplicated content.

Assess relevance and accuracy of the current content and improve links between
guides for similar tasks and concepts.

Proposed change
===============

1. Edit content for stylistic inconsistency and content accuracy:

  * Clean up existing content with grammar checks, use of definite articles,
    and verb subject agreement.
  * Address consistency of tables across the guides - adjust to a
    variable list with bold headings, or a table with :code: roles inside
    the cells to highlight commands.
  * Reorganize troubleshooting sections into a single format - change the
    Troubleshooting sections to use a "Problem" and "Solution" format
    used in the Block Storage Chapter.

2. Clarify the audience of each guide using a user task matrix and results
   from the OpenStack foundation administrator survey. Reorganize content
   appropriately.

3. Restructure the guides by merging content from the Cloud Administrator Guide
   into the Administrator User Guide and the User Guide as appropriate. Remove
   the Cloud Administrator Guide from openstack-manuals.

4. Rename the Administrator User Guide to Administrator Guide.

5. Remove the Python SDK source files from openstack-manuals, move the
   files to the api-site, and publish to developer-openstack.org. The
   current published files are at http://docs.openstack.org/user-guide/sdk/html
   and the source is at
   http://git.openstack.org/cgit/openstack/openstack-manuals/tree/doc/user-guide/source/sdk*.rst

Alternatives
------------

1. Implement only the first and second proposed changes, keeping three separate
   guides.

2. Implement only the first proposed change, editing the content as described.

3. Make no changes, and leave the guides as they are.

Implementation
==============

Assignee(s)
-----------
Joseph Robinson(joseph-r-email)

Brian Moss(kallimachos)

Other Contributors
------------------
The User Guide Team, and anyone willing to test procedures for accuracy or
proofread the guides.

Contact team leads not currently listed in the guides for
discussion on what tasks and actions are most useful and
needed for an Administrator Guide, and confirm
glossary items: Designate, CloudKitty, Magnum, and Zaqar.

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

Dashboard
~~~~~~~~~
* Check Liberty Dashboard updates and changes.

Compute
~~~~~~~
* AMPQ: introductory colons to introduce a list. Capitalize
  abbreviations in brackets - change (ampq) to (AMPQ).
* Hypervisors: Reorganize and link to the Admin User Guide. Include a
  section on how to use a hypervisor.
* Tenants, users, roles: remove passive voice. Link to the
  "How Can I Use The Cloud?" section of the End User Guide
  *Admin User Guide* - Create and manage roles - reorganize this content to
  align with the Cloud Admin Guide content.

EC2 compatibility
~~~~~~~~~~~~~~~~~
* Remove passive voice.
* Compare this section with the liberty installation guide.

Building Blocks
~~~~~~~~~~~~~~~
* Introduction: Clarify what base operating system is referred to here.
  Check content for accuracy.
* The nova image-list command. Link together the content on the nova
  command line client with the *End User Guide* here.

Images and Instances
~~~~~~~~~~~~~~~~~~~~
* Align the introduction with the *End User Guide*.
* Align the Launching instances and the Adding and removing resources
  section with the *Admin User Guide*.
* "This diagram shows the system state prior to launching an instances"
  Describe the parts of the diagram. The paragraph is not clear. Extend to
  the modifications to the other diagrams.

Networking with nova-network
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* Improving troubleshooting sections, as identified by recent research
  into user `nova-network to neutron adoption and migration`_.
* The Cloud Admin Guide references floating IP addresses, which users can
  change. The User Guide section on Networking will need reorganization to
  line up with this content. Information on how to assign IP addresses to VM's
  also needs testing.
* VLAN Network Manager: Check paragraph indentation.
* nova network-create vmnet: Address table consistency across guides.
* Configure Compute to use IPv6 addresses: Address table consistency
  across guides.

Metadata
~~~~~~~~
* Liberty to Mitaka-metadata services now include 'project_id' according to
  release notes.
* Metadata needs an SME check for currency. (Andrew Bogott, John Garbutt,
  Matthiew Gagne)
* Description of metadata config options table: Address table consistency
  across guides.

Flavors
~~~~~~~
* Flavors define these elements table: Address tables consistency
  across guides. (Bold headings with sentences here).
* Are the tables in the *Admin User Guide* on setting flavors effective?
* Show Host Usage Statistics: Host usage statistics description, and
  change to bold headings.

Secure with Rootwrap
~~~~~~~~~~~~~~~~~~~~
* Configuration option [Default]: SME to check, and change to better format.
  Might need a code snippet
* Migrate Instances: These tables were code snippets. Can they be
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
* Components: Edit passive voice usage, and adjust the opening sentence
  introducing the components. Move the descriptive opening sentence to
  the introduction, and into the *Admin User Guide* section on Object Storage.
* Rings: Underneath the Ring diagram, edit these sentences for a comma splice.
* Zones: Mentions the high availability plus other components already mentioned
  in the Components section. So, Components description is not needed. Edit for
  repetition.
* Partitions: Edit for punctuation - Comma Splice
* Change the Cluster Architecture and Ring Builder Sections within the Block
  storage chapter.
* Account Reaper: "In the background, the account reaper removes
  data from deleted accounts..." Edit the syntax here.
* Object Storage Monitoring - Excerpt from a blog. Keep or remove? This
  section also needs a syntax review.

Block Storage
~~~~~~~~~~~~~
* Block Storage: persistent storage needs to be mentioned earlier and more
  clearly in this introduction.
* Migrate volumes: These commands could appear in the *End User Guide*
* Block Storage command line list: "cinder-manager host lists",
  "cinder get-pools" Adapt for the *Admin User Guide*.
* Back up and Restore volumes: Is this procedure a cloud admin procedure, or
  can the basic information be adapted to the *Admin User Guide*? Requires role
  clarification.
* Clarify if the Transfer a volume section in the *Admin User Guide* is
  similar to the Export and import backup metadata procedure in the
  *Cloud Admin Guide*.
* Configure and use volume number weigher: This procedure references cinder
  commands described in the *End User guide* and *Cloud Admin Guides*.
  Reorganize this content.
* Supported Operations in filter and goodness
  functions: Remove passive voice in the
  Caution note.
* Rate-limit volume copy Bandwidth: Reorganize the guide such that
  this content appears closer to the information on moving and
  migrating block storage volumes
  ("volume_copy_bps_limit").
* Image volume cache: Remove passive voice.
* Get capabilities: This section describes actions an administrator
  can take with an API,
  capability investigation. Reorganize this information with the
  *Admin User Guide*.
* Multipath call failed exit: This Troubleshooting section
  recruits a Problem and Solution heading architecture useful
  for the other Troubleshooting sections of the
  Cloud Admin Guide.

Shared File System
~~~~~~~~~~~~~~~~~~
* Key Concepts: Remove passive voice.
* Share basic operations: " General concepts " edit or clarify this phrase.
* Manila commands show, update, and delete options could appear in the
  *Admin User Guide*. Clarify Shared File System responsibilities.
* Manage and unmanage share: Edit missing words in some sentences
* Resize a share: Also missing words here.
* Quotas and Limits: Edit verb subject agreement.
* Share snapshots: Include the manila snapshot-create command listed in
  the *Admin User Guide* here.
* Consistency group: Edit verb subject agreements ("admin to admins").
* Scheduling: Edit for article and definite articles.
* Networking - Edit for missing words.
* Share networks - Edit verb subject agreements

Networking
~~~~~~~~~~
* Plug-in configurations section: Document the most common ml2 plug-in
  configurations.
* Reference network option plugins for ml2
  http://docs.openstack.org/liberty/config-reference/
  content/networking-options-plugins-ml2.html.
  See https://bugs.launchpad.net/openstack-manuals/+bug/1411624
* Use Networking section: Networking Tables need consistency with the
  other *Cloud Admin Guide* tables.
* Networking Architecture: This section's description of architecture
  would be better placed following the introduction.
* Configuring Identity for Networking: A note about not using Nova-network
  with compute appears here,
  but needs to appear earlier - the introduction - as a warning for cloud
  administrators.

Database
~~~~~~~~
* No recommended changes currently.

Baremetal
~~~~~~~~~
* No recommended changes currently.

Orchestration
~~~~~~~~~~~~~
* No recommended changes currently.

Telemetry
~~~~~~~~~
* Data Retrieval: The code snippet tables need to fit the page.
* Measurements: Confirm that no other measurement items are added
  from the Liberty release.

Orchestration
~~~~~~~~~~~~~
* Orchestration Authorization Model: This section requires an edit for grammar.
* Stack domain users: Grammar Edits also required for this section.
* Cross-origin resource sharing: The sub-section "enabling CORS with
  configuration" needs an edit to change into a procedure
  rather than a list of items.

Cross-project features
~~~~~~~~~~~~~~~~~~~~~~
* No recommended changes currently

Redirects and Build Jobs
~~~~~~~~~~~~~~~~~~~~~~~~
* File redirects and performing build jobs as needed is also
  required.

Project Scope
=============

* OpenStack's project navigator describes project maturity. Statistics
  listed on the `Project Navigator`_ page cover the project Age,
  adoption percentage, stable branch presence, corporate diversity,
  SDK support, and install guide content.

* OpenStack projects with longevity, that comply with several of these
  statistics, include Nova, Neutron, Swift, Cinder, Keystone, Glance,
  Horizon, and Heat. The scope of this reorganization will improve content
  on these services accross the guide, but without large scale changes.

* More recently developed project still seeking more maturity indicators,
  that may also be 3 or less years into their development, include
  *Zaqar*, *Murano*, *Sahara*, and *Trove*. *Manila* content requires
  attention, which is described in the Shared File System section
  under the Work Items heading. The scope of this reorganization
  extends to including content from these more recent projects.
  Introducing or improving new content from more recent projects is
  a large scale change for this reorganization.

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
  items can be recorded in the `User Guide Etherpad`_.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/User_Guides

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

.. _`User Guide Etherpad`: https://etherpad.openstack.org/p/UserGuideSpecification

.. _`Project Navigator`: http://www.openstack.org/software/project-navigator

.. _`nova-network to neutron adoption and migration`: https://wiki.openstack.org/wiki/HorizonUsability_Testing#Results_Presentation
