..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============================================
 Retention Policy for Published Documentation
==============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/retention-policy

The `2017 User survey`_ highlights the fact that many of our users are
still deploying and otherwise working with versions of OpenStack for
which upstream support is no longer available. These end-of-life
versions are still clearly useful to some users, and to improve their
experience we should continue to make the documentation for those
releases available.

Problem description
===================

The current retention policy for published documentation calls for
manuals to be removed from docs.openstack.org when the associated
branches are marked "end of life" and closed.  The older documentation
has been removed from the site in the past for several reasons. In no
particular order:

* **Content size**

  The amount of content we were publishing was quite large for the
  hosting service being used at the time.

* **Search results**

  * Removing older documentation was seen as reducing confusion
    because users searching without specifying a version number or
    series name would not encounter information that was out of date.

  * Documentation for older releases, by virtue of having longer lived
    stable URLs, was appearing higher in search results than similar
    updated content for newer releases.

* **Support requests**

  Bugs and support requests have been filed for versions of the
  documentation that will no longer be updated or fixed. This caused
  undue burden to the documentation team.

* **Build support**

  After the stable branch for the documentation was closed, there was
  no longer a way to build and update the published
  documentation. This is not an issue with regard to content, but we
  have had at least one situation where there was a security issue for
  a cross-site-scripting attack that pointed out if we had similar
  problems in the future with dynamic aspects of the site for branches
  that could no longer be built, deleting the content may be the only
  action we could take. See commit
  de6289854e9a059d5a33075b6593e7f9cb3b4f2d in the
  clouddocs-maven-plugin repository for details (that repository is
  not indexed via gerrit or available via the cgit web UI for some
  reason).

We are updating this policy for two reasons:

1. According to the latest user survey at the time of this writing,
   around 60% of users running a version of OpenStack no longer
   supported upstream. These users are left without accurate
   documentation for the versions of software that they are deploying.

2. As part of the :doc:`../pike/os-manuals-migration` initiative, more
   of the actively maintained documentation is now managed by project
   teams outside of the ``openstack-manuals`` git repository.

Proposed change
===============

The proposed change is to stop deleting all content from
docs.openstack.org based on its age, or the age of the software to
which it applies or the repository from which it was recovered.

We will also recover the admin guide, CLI reference, and user guide
for Mitaka through Ocata. The admin guide is meant to be reusable
between series, but that is only true when the underlying operating
system does not change. Since it has changed in the past, we need to
view the admin guide as series-specific *even when we do not change
it*. The CLI reference and user guide for Mitaka use the old versions
of the clients, and the options may have changed since then.

The Mitaka series was selected for several reasons.

1. It is the first series for which all of the documentation was
   managed using Sphinx, which is easier to install than the older
   tools and we have more knowledge throughout the community for
   working with Sphinx.

2. It also represents a sufficiently old version to be useful to a
   large number of users. The combination of utility and ease of
   updating makes Mitaka a good compromise point for starting the new
   retention policy.

3. Much of the project-specific documentation from the Mitaka release
   still exists on docs.openstack.org so it will be easy to link to
   it.

We will find other ways to mitigate the issues that motivated us to
adopt the old policy of deleting end-of-life releases.

The documentation for end-of-life releases will still be frozen when
the relevant stable branches are closed, so no updates will be
made. This change should not significantly expand the maintenance
burden or expectations of users.

* **Content size**

  We have already migrated docs.openstack.org off of the CloudSites
  hosting service to a standard web server with a large
  filesystem. The amount of content we are publishing is no longer a
  significant issue.

* **Search results**

  Given the number of users running older versions, our priorities for
  search results have changed. We *want* old versions to be available
  via search engines, assuming the user can easily determine whether
  the results they have found match their version or that they can
  navigate between versions quickly.

  We will continue to experiment with search engine optimization
  techniques to have unqualified searches like "installing nova" show
  newer results. That work will have its own spec, to be created by
  the team that takes on the task.

  We can make navigating between series-specific docs easy by taking
  advantage of the ``earliest_published_series`` `configuration option
  for the
  theme. <https://docs.openstack.org/openstackdocstheme/latest/>`__

  We will also update the documentation theme to include a watermark
  or "badge" clearly indicating when content is considered old and
  especially when it is no longer maintained. These markers need to be
  built outside of the documentation itself so they can be updated
  independently, without patching the docs or adding steps to the
  stable branch EOL process. The plan discussed at the Queens PTG was
  based on SVG files built from the openstack-manuals repository and
  included into published pages by the ``openstackdocstheme``. More
  details need to be worked out, and that work will involve its own
  spec to follow this one.

* **Support requests**

  Project teams are now responsible for project-specific
  documentation. Bugs and support requests that come in to the
  documentation team can be triaged and reassigned to project teams as
  needed. Anything related to documentation that is no longer
  supported should be treated the same way as bug reports for
  unsupported code (closed "wontfix").

* **Build support**

  Because we are not extending the supported lifetime for stable
  branches and the documentation they contain, the only reasons to
  need to build the docs are if we lose the data on the web server or
  if there is another security issue. After a branch is closed, no
  more updates to the documentation for that branch need to be
  considered.

  While we do not want to downplay the seriousness of potential issues
  with cross-site scripting or JavaScript CVEs, we also do not want to
  over-emphasize the likelihood of such issues coming up. If such
  issues do arise, we will work on a resolution at that time. In a
  worst-case scenario where restoring stable branches and changing the
  builds does not work, and manual updates of the affected files are
  not possible, we can delete the bad content. Any decision about the
  best course of action will be made at the time by the people
  actively working on the problem.

  Similarly, if we experience a loss of data on the web server and
  need to rebuild content, the people managing the recovery can
  develop a plan when needed.

Alternatives
------------

#. Do nothing.

   This option is not appealing because we have had clear and loud
   requests from users to help them in this area.

#. Suggest that users build local copies of the documentation for old
   releases.

   Some users have resorted to trying to build their own internal
   copies of the documentation to continue to manage their
   deployments. They have found issues with the documentation at the
   ``$series-eol`` tags no longer building properly because external
   references to things like sample files in git repositories are not
   present.

#. Create ``docfixes`` branches, similar to the ``driverfixes``
   branches used by project teams to allow vendors to collaborate on
   patches to drivers after a version of the software has been marked
   EOL. The ``docfixes`` branches would be allowed to build only the
   documentation and update the published content on
   docs.openstack.org (they would not be used for new releases of
   software or code patches not related to documentation).

   Without a significant number of contributors to review and manage
   pages in these branches, it seems unlikely that we would see any
   benefit from keeping them open. If the contributions to the
   existing stable branches increase, we can reconsider this option in
   the future.

#. Archive the content in non-indexed formats such as tarballs.

   The old archival spec approved for Pike but never implemented
   requires much more manual work and active management of old
   content. Simply leaving the content in place on the web server is
   more sustainable with a small documentation team.

Implementation
==============

Assignee(s)
-----------

Primary assignees:

* dhellmann

Other contributors:

* pkovar

Work Items
----------

* Restore the stable/mitaka version of the admin, CLI, and user guides
  are published using series-specific URLs. (dhellmann)

  * Create a new ``stable/mitaka`` branch.
  * Update the build scripts so the manuals are published to
    series-specific URLs.
  * Add appropriate redirects.
  * Re-close the branch.

* Update the stable/ocata branch of openstack/openstack-manuals to
  build the admin, CLI, and user guides using series-specific
  URLs. (*owner needed*)

  * Update the build scripts so the manuals are published to
    series-specific URLs.
  * Add appropriate redirects.
  * Update the stable/newton branch of openstack/openstack-manuals to
    link to the Ocata versions of the admin, CLI, and user guides.

* Write a spec for the version "badges" and implement the appropriate
  changes. (*owner needed*)

Dependencies
============

None

Testing
=======

Old documents will be recovered as-is, and only changes needed to
update the publication locations and ensure the builds work will be
allowed.

References
==========

* `2017 User survey`_

.. _2017 User survey: http://superuser.openstack.org/articles/2017-openstack-user-survey-insights/

* Mailing list threads

  * `July 2017 (docs list)
    <http://lists.openstack.org/pipermail/openstack-docs/2017-July/thread.html#10069>`__
  * `July 2017 (dev list)
    <http://lists.openstack.org/pipermail/openstack-dev/2017-July/thread.html#120254>`__
  * `August 2017 (dev list)
    <http://lists.openstack.org/pipermail/openstack-dev/2017-August/thread.html#120541>`__

* `Notes from discussion at the Queens PTG
  <https://etherpad.openstack.org/p/docs-i18n-ptg-queens>`__

* `Old "Archiving" spec
  <http://git.openstack.org/cgit/openstack/docs-specs/commit/?id=4ce480f4e29d8514a8b01acbe8157d84ed731d04>`__

* `Old "Archiving" blueprint
  <https://blueprints.launchpad.net/openstack-manuals/+spec/archiving>`__
