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
scenario where updates to the administrator guide are an after thought if they
get updated at all.  "DocImpact" bugs essentially throw the problem over the
fence to the documentation team with little description of the required
changes.

Proposed change
===============

This specification proposes managing the administrator guide similar to the
installation guide, where the administrator guide contents are stored in the
project repository and are directly managed but the project team.  The
documentation team would provide an editorial role for the contents of the
administrator guide by posting patches to the guide contents in the project
repositories.  This would allow for the continued consistent quality and voice
of the guide.

Existing administrator guide content would be migrated to the designated
project repositories. Project teams can decide which repository is appropriate
for the content, for example neutron may choose openstack/neutron-lib. Inside
these repositories the administrator guide content will be stored in a well
known and consistent location, admin-guide/source. The current adminstrator
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
contents. This is similar to how the i18n team prioritizes projects for
localization.

New gate jobs can be added to the project repositories that look for changes
in the ^admin-guide/.* path on patch commits that open a docimpact style
bug for the docs team to provide an editorial review of the changes. Using
this mechanism means that the bug will have a direct link to the patch that
included changes to the administrator guide content.

At patch commit and merge time, the admin-guide gate jobs can integrate the
project based administrator guides by checking out the required repositories
and storing symbolic links in the main openstack-docs repository to each
of the project's admin-guide/source directories.

The administrator guide should be structured:

::

   [openstack-docs/admin-guide/index.rst]
    ===================
    Administrator Guide
    ===================
        .. toctree::
            compute/index.rst (compute is a symbolic link to
                               nova/admin-guide/source)
            networking/index.rst (networking is a symbolic link to
                                  neutron-lib/admin-guide/source)
            ...

    [nova/admin-guide/source/index.rst]
    =======
    Compute
    =======
    * System architecture
    * Images and instances
    ...

This structure would allow a complete documentation set to be created.

Alternatives
------------

1. Do nothing and attempt to maintain a centralized documentation repository.
2. Create a documentation repository for each project with shared core status.
3. Follow the proposed changes, but allow the documenation team core status.

Implementation
==============

Assignee(s)
-----------


Work Items
----------
* Setup admin-guide folders in the appropriate project repositories.
* Move existing content from the central administrator guide into the per
  project repositories.
* Create the list of repositories that will be required to render the guide.
* Setup gate jobs to open "docimpact" style bugs on ^admin-guide/.* commits.
* Setup gate jobs to render the administrator guide on patch upload and merge.

Dependencies
============
* This model implies that the administrator guide and the participating
  projects are using stable branches such that release specific guides are
  available.

Testing
=======


References
==========

* https://etherpad.openstack.org/p/docs-i18n-ptg-pike-repos
* https://github.com/openstack/docs-specs/blob/master/specs/newton/project-specific-installguides.rst
