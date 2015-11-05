..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

.. _config_ref_mitaka_rst:

=======================================
Configuration Reference: RST conversion
=======================================

https://blueprints.launchpad.net/openstack-manuals/+spec/config-ref-rst

Convert the Configuration Reference from DocBook to RST.

Problem description
===================

The Configuration Reference will be converted from DocBook to RST for the
Mitaka release. The tools generating the configuration options tables will be
modified to generate RST tables instead of docbook tables.

Proposed change
===============

Convert the Configuration Reference to RST.

Update the ``autohelp.py``, ``diff_branches.py`` and ``extract_swift_flags.py``
scripts to generate the configuration options tables.

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* gpocentek

Work Items
----------

* Update the openstack-doc-tools scripts to support RST output.

* Convert content from DocBook to RST.

* Ensure bug fix proposals are included in DocBook and RST during the
  conversion process.

* Track changes in wiki_.

.. _wiki: https://wiki.openstack.org/wiki/Documentation/Migrate

* Update our build infrastructure so that Sphinx is used for publishing the
  Configuration Reference.

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
  #openstack-doc, the openstack-docs mailing list with [config-ref] in the
  subject, weekly `documentation team meeting`_, and potentially etherpads.

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting


* `Migration wiki`_

.. _`Migration wiki`: https://wiki.openstack.org/wiki/Documentation/Migrate
