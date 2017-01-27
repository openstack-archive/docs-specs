..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=================================================
Archiving old documentation on docs.openstack.org
=================================================

Problem description
===================

As of the time of drafting, the docs.openstack.com site retention policy is
to publish the current release (Newton), plus two previous releases (Mitaka
and Liberty). This retention policy is in line with Foundation support
arrangements (see References).

According to the last User Survey (see References), 9% of production OpenStack
installations were still running Icehouse, 17% were running Juno, and 40% are
running Kilo.

This would indicate that a significant number of users are relying on
documentation that could potentially disappear in accordance with our current
retention policy.

Proposed change
===============

* At every new release, the release becoming EOL'd is moved to a read-only
  archive folder (this can be completed with a script, TBD).
* The archive folder is made available online for people to download the
  branch they require as a tar.gz file.
* Note somewhere obvious that documents in the archive are not editable, and
  bugs raised against them will be closed WONTFIX.

Notes
-----

* This solution would cover all documentation in /$EOLRELEASE on
  docs.openstack.org, including /developer, in order to simplify the process.
* Books that are already versioned (Install Guide, Config Ref, and CLI Ref)


Alternatives
------------

* Maintain the status quo (Do nothing)
* About a million other things

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  * Documentation team

Other contributors:
  * Lana Brindley (loquacities)
  * Alexandra Settle (asettle)
  * Brian Moss - Docs Tools (bmoss)
  * Andreas Jaeger - Infra (ajaeger)

Work items
----------

* Develop script for archiving (Infra)
* Investigate the possibility of archiving only PDF versions (Infra)
* Use Sphinxmark to watermark old versions, and add note about bugs (Tools)
* Implementation

Dependencies
============

* Infra assistance

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* OpenStack supported releases: <https://releases.openstack.org/>`_
* OpenStack User Survey snapshot results, October 2016:
  <https://www.openstack.org/assets/survey/October2016SurveyReport.pdf>`_
* This conversation was triggered by:
  <https://bugs.launchpad.net/openstack-manuals/+bug/1658659>`_
* Mailing list conversation:
  <http://lists.openstack.org/pipermail/openstack-docs/2017-January/009493.html>`_
* Meeting discussion:
  <http://eavesdrop.openstack.org/meetings/docteam/2017/docteam.2017-01-26-21.03.log.html>`_
