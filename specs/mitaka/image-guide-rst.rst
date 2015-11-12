..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

.. _image_guide_rst:

===========================================
Virtual Machine Image Guide: RST conversion
===========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/image-guide-rst

Convert the Virtual Machine Image Guide from DocBook to RST.

Problem description
===================

The Virtual Machine Image Guide will be converted from DocBook to RST
for the Mitaka release.

Proposed change
===============

Convert the Virtual Machine Image Guide to RST.

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* kato-tomoyuki

Work Items
----------

* Ensure bug fix proposals are included in DocBook and RST during the
  conversion process.

* Track changes in wiki_.

.. _wiki: https://wiki.openstack.org/wiki/Documentation/Migrate

* Update our build infrastructure so that Sphinx is used for publishing the
  Virtual Machine Image Guide.

* Apply the openstackdocstheme template to the guide.


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
  #openstack-doc, the openstack-docs mailing list with [image-guide]
  in the subject, weekly `documentation team meeting`_, and
  potentially etherpads.

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

* `Migration wiki`_

.. _`Migration wiki`: https://wiki.openstack.org/wiki/Documentation/Migrate

