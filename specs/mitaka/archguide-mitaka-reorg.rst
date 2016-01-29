..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Improve the Architecture Design Guide
==========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/archguide-mitaka-reorg

Reorganize and update the Architecture Design Guide.

Problem description
===================

Currently, the Architecture Design Guide is primarily organised by use case.
However, a combination of features from different use cases is often used when
designing an OpenStack cloud.

It is recommended to reorganise information so the user can consider all the
requirements first, to help determine their OpenStack cloud architecture.
Additional information should be provided when designing an OpenStack
cloud in a development, staged or production environment. The initial proposal
is to reorganise cloud design requirements into chapters, and
consolidate use case examples into a single chapter.

Proposed change
===============

Reorganize and update the guide to improve usability and accessibility of
information. Proposed table of contents:

  1. Introduction
  2. Identifying stakeholders
  3. Functional requirements
  4. User requirements
  5. Operator requirements
  6. Capacity planning and scaling
     6.1 Storage
     6.2 Networking
     6.3 Compute
  7. High availability
  8. Security requirements
  9. Legal requirements
  10. Example architectures (reflecting concepts and terminology described in
      previous chapters)

Alternatives
------------

- Leave the guide as it is.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* dazzachan

Other contributors:

* Ops Guide specialty team

Work Items
----------

* Reach a consensus on the information architecture
* Rework the abstract to clearly identify the audience and purpose of the book
* Move content to improve information architecture
* Identify information gaps and submit and fix bugs

Dependencies
============

This work is dependent on the guide being converted from DocBook to RST. See
:ref:`archguide-mitaka-rst`.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [arch-guide]
  in the subject, weekly Ops Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

  .. _`specialty team meeting`:
     https://wiki.openstack.org/wiki/Documentation/OpsGuide

  .. _`documentation team meeting`:
     https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

* `Docs swarm etherpad`_

  .. _`Docs swarm etherpad`:
     https://etherpad.openstack.org/p/openstack-swarm2015

* `Docs swarm specification`_

  .. _`Docs swarm specification`:
     http://specs.openstack.org/openstack/docs-specs/specs/liberty/arch-guide.html

