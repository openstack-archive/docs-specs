..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================
Distributed Admin Guides
========================

The number of approved OpenStack projects continues to grow while the
documentation team resources are shrinking. We need a new approach to maintain
the high quality of the OpenStack documentation set.

This specification proposes allowing project teams to manage their
administrator guide content similar to how the api-ref and installation guides
are being managed.

Problem description
===================

Currently there are over sixty approved OpenStack projects. It is unreasonable
to expect the documentation team to maintain the administrator guide for all
of these projects. We need to optimize our usage of the documentation team's
limited resources.

Currently the administrator guide is in a seperate git repository from the
code and patches being proposed.  This leads to an "out of site, out of mind"
scenario where updates to the administrator guide are an afterthought if they
get updated at all.

Proposed change
===============

This specification proposes managing the administrator guide similar to the
installation guide, where the administrator guide contents are stored in the
project repository and are directly managed by the project team.  The
documentation team can continue to provide an editorial role for the contents
of the administrator guide by posting patches to the guide contents in the
project repositories. This would allow for the continued consistent quality
and voice of the guide.

Existing administrator guide content would be migrated to the designated
project repositories. Project teams can decide which repository is appropriate
for the content, for example neutron may choose openstack/neutron-lib. Inside
these repositories the administrator guide content will be stored in a well
known and consistent location: admin-guide/source. The current administrator
guide is already laid out by service/project so this proposal should have
minimal impact to the look and feel of the guide.

Ownership of the project specific administrator guides is with the
respective project team, not the documentation team. This means the
content is in an existing or new repository owned by the project team,
reviews will be done by the project team, and bug reports will go in
the bug queue of the project.

The documentation team enables the project team to write the
project specific guides with mentoring, setting up needed
infrastructure, writing guidelines, provision of a template ("cookie
cutter"), and providing a working base administrator guide that the project
specific guides can use as reference.

The documentation team will select a list of priority projects for the release
series that will get a full review and scrub of the administrator guide
contents for those selected projects. This is similar to how the i18n team
prioritizes projects for localization.

To publish the project's administrator guide, the project will implement a tox
target to build the guide, similar to the one created for the installation
guides (see References). A gate job template 'admin-guide-jobs' will be added
to the project including the service name.  This will cause the administration
guide to be published when updates are merged.

This publication mechanism should be similar that of the installation guide.

The administrator guide should be structured:

::

   [openstack-docs/admin-guide/index.rst]
    ====================
    Administrator Guides
    ====================

    Compute service (nova)
    ======================

    The Compute service ...

    Installation is documented at
    http://docs.openstack.org/project-admin-guide/pike/compute

    Loadbalancer service (octavia)
    ======================

    The Loadbalancer service ...

    Installation is documented at
    http://docs.openstack.org/project-admin-guide/pike/loadbalancer
    .

    [nova/admin-guide/source/index.rst]
    =======
    Compute
    =======
    * System architecture
    * Images and instances
    ...

One difference with the administrator guide from the installation guide is
that all of the administrator guides are listed on one page. This makes it
easier for users to find any of the official OpenStack project administrator
guides.

With this change the administrator guide will now be versioned by release to
allow version specific content.  This will be handled the same way the
installation guide is versioned.  Administrator guides built from master will
be published to "draft" while stable branches will publish to the respective
release directory.

::

  The master branch of octavia would publish to:
  http://docs.openstack.org/project-admin-guide/draft/loadbalancer

  The stable/pike branch of octavia would publish to:
  http://docs.openstack.org/project-admin-guide/pike/loadbalancer

Alternatives
------------

1. Do nothing and attempt to maintain a centralized documentation repository.
2. Create a documentation repository for each project with shared core status.
3. Follow the proposed changes, but allow the documentation team core status.

Implementation
==============

Assignee(s)
-----------
Alexandra Settle (asettle)
Joseph Robinson (jrobinson\_)
Michael Johnson (johnsom)
Ildiko Vancsa (ildikov)
Brian Moss (Docs tools)
Entire documentation team


Work Items
----------
* Setup a wiki page to track the transition.
* Setup cookiecutter for the administrator guide.
* Encourage the project teams to move existing content to project team
  repositories.
* Update the master index file to reflect the new structure.
* Write a base administrator guide.
* Setup gate jobs to publish the administrator guide on patch merge.
* Update the Documentation Contributor Guide to include the required steps
  to setup a project administrator guide.
* Notify project teams when this method of publishing the project specific
  administrator guide is available.

Dependencies
============

Testing
=======


References
==========

* https://etherpad.openstack.org/p/docs-i18n-ptg-pike-repos
* https://github.com/openstack/docs-specs/blob/master/specs/newton/project-specific-installguides.rst
* https://docs.openstack.org/contributor-guide/project-install-guide.html
