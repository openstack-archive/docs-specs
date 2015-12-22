..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

.. _cli_ref_rst:

================================================
Command-Line Interface Reference: RST conversion
================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/cli-ref-rst

Convert Command-Line Interface Reference from DocBook to ReST.

Problem description
===================

Command-Line Interface Reference uses old DocBook format.
Currently, we use the new docs theme with ReST format.

Proposed change
===============

Convert the Command-Line Interface Reference from DockBook to ReST.

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

* Stop updating the entire guide.

* Modify the output by the command reference generation tool
  from DocBook to ReST.

* Convert the manual contents from DocBook to Rest.

* Track changes in wiki_.

.. _wiki: https://wiki.openstack.org/wiki/Documentation/Migrate

* Update our build infrastructure so that Sphinx is used for
  publishing the Command-Line Interface Reference.

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

