..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

.. _ops-guide-rst:

==========================================
Operations Guide: RST conversion
==========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/ops-guide-rst

Convert the Operations Guide from DocBook to RST.

Problem description
===================

The Operations Guide will be converted from DocBook to RST for the
Mitaka release. This conversion is a precursor to reorganising the guide.

Proposed change
===============

Convert the Operations Guide to RST.

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* dazzachan

Other contributors:

* shilla-saebi
* alexandra-settle
* kato-tomoyuki

Work Items
----------

* Convert content from DocBook to RST

* Ensure bug fix proposals are included in DocBook and RST during the
  conversion process.

* Track changes in wiki_.

.. _wiki: https://wiki.openstack.org/wiki/Documentation/Migrate

* Update our build infrastructure so that Sphinx is used for publishing the
  Operations Guide.

* Apply the openstackdocstheme template to the guide.

* Import translations from the old guide to the new guide.


Dependencies
============

The main dependency is on docs.openstack.org infrastructure updates.

Testing
=======

* Test the new HTML design on the following browsers/operating systems:

  * Chrome on Ubuntu, Fedora, Mac, Windows
  * Firefox on Ubuntu, Fedora, Mac, Windows

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [ops-guide]
  in the subject, weekly Ops Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/OpsGuide

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting


* `Migration wiki`_

.. _`Migration wiki`: https://wiki.openstack.org/wiki/Documentation/Migrate

