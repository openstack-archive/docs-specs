..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=================================================
Archiving old documentation on docs.openstack.org
=================================================

Problem description
===================

As of the time of drafting, the docs.openstack.org site retention policy is
to publish the current release (Newton), plus two previous releases (Mitaka
and Liberty). The retention policy was initially designed to match the "End
of Life" support policy that project branches adhere to, which is documented
as indicating stable branches (see References). Because the project code
would not be supported, the docs were removed from the docs site, to match
the project code branch strategy.

According to the last User Survey (see References), 9% of production OpenStack
installations were still running Icehouse, 17% were running Juno, and 40% were
running Kilo.

This would indicate that a significant number of users are relying on
documentation that could potentially disappear in accordance with our current
retention policy.

Historical note: When the documentation pages were created in 2010, they were
hosted on Rackspace Cloud Sites without a clear retention policy, which
resulted in a large number of unmanaged files over many years. The docs.o.o
site was the largest site on Cloud Sites at the time, which resulted in Cloud
Sites specifically asking us to remove old content. Change in hosting provider
was eventually enforced on the team by the sale of Cloud Sites to Liquid Web
in 2016, and the site is now hosted on internal OpenStack infrastructure, and
the current retention policy was decided upon at the Barcelona Summit in
October 2016.

Proposed change
===============

* At every new release, the release becoming EOL'd is moved to a read-only
  archive folder (this can be completed with a script, TBD).
* The archive folder is made available online for people to download the
  branch they require as a tar.gz file.
* The archive folder should be accessible from the openstack-manuals repo,
  and delivered publicly from the docs.openstack.org site.
* Note somewhere obvious that documents in the archive are not editable, and
  bugs raised against them will be closed WONTFIX.
* Develop a procedure for taking a certain git history SHA and creating the
  documentation locally. Write this up in the Contributor Guide.

Notes
-----

* This solution would cover all documentation in /$EOLRELEASE on
  docs.openstack.org, including /developer, in order to simplify the process.
* This covers books that are already versioned (Install Guide, Config Ref,
  and CLI Ref), but could potentially be expanded to all books.
* We will need to determine a threshold for deleting documentation from the
  archive permanently. This can be achieved through a community discussion.
* All documentation history and tags will remain in the git repository, so it
  is always possible to checkout old versions, even if they are not published.
* Can we do something like archive.openstack.org? Also, maybe a link to
  archives from the main docs site.


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
  * Anne Gentle (annegentle)

Work items
----------

* Develop script for archiving (Brian & Infra)
* Investigate the possibility of archiving only PDF versions (Brian & Infra)
* Use Sphinxmark to watermark old versions, and add note about bugs (Brian & Tools)
* Implementation
* Document the procedure for restoring documentation from a git repo at a
  certain point-in-time (Anne)

Dependencies
============

* Infra assistance

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* OpenStack supported releases: `<https://releases.openstack.org/>`_
* OpenStack "End of Life" support policy: `<http://docs.openstack.org/project-team-guide/stable-branches.html/>`_
* OpenStack User Survey snapshot results, October 2016:
  `<https://www.openstack.org/assets/survey/October2016SurveyReport.pdf>`_
* This conversation was triggered by:
  `<https://bugs.launchpad.net/openstack-manuals/+bug/1658659>`_ and
  `<https://bugs.launchpad.net/openstack-manuals/+bug/1621685>`_
* Mailing list conversation:
  `<http://lists.openstack.org/pipermail/openstack-docs/2017-January/009493.html>`_
* Meeting discussion:
  `<http://eavesdrop.openstack.org/meetings/docteam/2017/docteam.2017-01-26-21.03.log.html>`_
