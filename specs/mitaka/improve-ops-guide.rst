..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Improve the Operations Guide
==========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/improve-ops-guide

Reorganize and update the Operations Guide.

Problem description
===================

The Operations Guide has become outdated over time, with identified gaps in
content.

Proposed change
===============

Based on doc sessions at the Mitaka summit, reorganize and update the guide
to improve usability and accessibility of information.

Alternatives
------------

Leave the guide as it is.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* shilla-saebi

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
:ref:`ops-guide-rst`.

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

* `Kilo operations midcycle meetup etherpad`_

  .. _`Kilo operations midcycle meetup etherpad`:
     https://etherpad.openstack.org/p/PAO-ops-ops-guide-fixing


