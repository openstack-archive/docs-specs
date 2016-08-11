..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===============================================
Use openstack command to replace other commands
===============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/use-openstack-command

Use the ``openstack`` command-line client to replace project specific commands
to promote consistency across the docs.

Problem description
===================

Docs historically use the individual command-line clients,
but we have the unified openstack CLIs at now, which deprecates
the individual CLIs. Therefore, we should use the ``openstack``
commands as possible.

Proposed change
===============

Use the ``openstack`` command-line client command to replace other commands
as possible as it is implemented.

Alternatives
------------

Leave the commands as they are.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* qiaomin032

Other contributors:

* caoyuan

Work Items
----------

* Use the ``openstack`` command to replace other commands.

Dependencies
============

None.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with
  in the subject, weekly Ops Guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

  .. _`specialty team meeting`:
     https://wiki.openstack.org/wiki/Documentation

  .. _`documentation team meeting`:
     https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

* `Kilo operations midcycle meetup etherpad`_

  .. _`Kilo operations midcycle meetup etherpad`:
     https://etherpad.openstack.org/p/PAO-ops-ops-guide-fixing


