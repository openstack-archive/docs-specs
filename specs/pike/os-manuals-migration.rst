===================================
OpenStack manuals project migration
===================================

Problem description
~~~~~~~~~~~~~~~~~~~

The documentation team are rapidly losing key contributors and core reviewers.
We are not alone, this is happening across the board. It is making things
harder, but not impossible.
Since our inception in 2010, we’ve been climbing higher and higher trying to
achieve the best documentation we could, and uphold our high standards.
However, we now need to take a step back and realise that the amount of work
we are attempting to maintain is out of reach for the team size that we have.
At the moment we have 13 cores, of whom none are full time contributors or
reviewers.

Until this point, the documentation team has owned several manuals that
include content related to multiple projects, including an installation
guide, admin guide, configuration guide, networking guide, and security
guide. Because the team no longer has the resources to own that content,
we want to invert the relationship between the doc team and project teams,
so that we become liaisons to help with maintenance instead of asking for
project teams to provide liaisons to help with content. As a part of that
change, we plan to move the existing content out of the central manuals
repository, into repositories owned by the appropriate project teams.
Project teams will then own the content and the documentation team will
assist by managing the build tools, helping with writing guidelines and
style, but not writing the bulk of the text.

We currently have the infrastructure set up to empower project teams to
manage their own documentation in their own tree, and many do. As part of
this change, the rest of the existing content from the install guide and
admin guide will also move into project-owned repositories.

Proposed change
~~~~~~~~~~~~~~~

Combine all of the documentation builds, so that each project has a single
doc/source directory that includes developer, contributor, and user
documentation. This option would reduce the number of build jobs we have to
run, and cut down on the number of separate sphinx configurations in each
repository.

In order for a single doc build job to work and make it easy to include links
from the landing pages on docs.openstack.org, we need to ensure a minimum level
of consistency in the organization of the docs directory. The sections are
based on the existing high-level groupings for which there are already landing
pages on docs.openstack.org that will need to be updated. Within each
top-level directory, project teams are free to organize their content
however seems most appropriate to them. This is the proposed layout
for phase 1:

* doc/source/
  * install/ -- anything having to do with installation of the project
  * contributor/ -- anything having to do with contributing to the project
    (applies to most of the current content under /developer, but not all
    contributors are developers and "developer" can be interpreted as
    "contributor" and "user of this library")
  * configuration/ -- automatically generated (we hope) configuration reference
    information as well as (we further hope) prose explaining what all of those
    options mean and how to use them sensibly
  * cli/ -- anything having to do with using command line tools
  * admin/ -- any admin guide content
  * library/ -- any reference and user information associated with a library
    that is not covered by one of the above categories

During a later phase, we will merge the API reference and release notes builds
into the same job, along with the rest of the documentation for a project.
Both of those builds have custom considerations, though, and it is more
important to move the content that is no longer going to be maintained
by the documentation team.

* doc/source/
  * api/ -- the REST API reference
  * releasenotes/ -- reno directions (the actual release notes inputs will stay
  in /releasenotes/notes, where they are now)

A new documentation build job will be set up to take the output produced from
``tox -e venv -- python setup.py build_sphinx`` (matching the existing
`Consistent Testing Interface"
<https://governance.openstack.org/tc/reference/project-testing-interface.html>`_)
and publish it to a new location under `<http://docs.openstack.org>`_
The results will go to:

* docs.openstack.org/$project-name/latest -- build from master
* docs.openstack.org/$project-name/$series -- build from stable/$series
* docs.openstack.org/$project-name/latest/$lang -- build translated version from
  master
* docs.openstack.org/$project-name/$series/$lang -- build translated version
  from stable/$series

Because we plan to reuse the existing `doc/source` directory in each project,
some of the existing content will need to be rearranged as part of importing
the content from openstack-manuals.

Ultimately, this changes the way we publish results, and redirects will be
required to be setup from all of the existing locations to the new locations,
and move all of the existing documentation under the new structure. We will
retain landing pages for the high level categories such as the install guides,
the configuration reference, and contributor documentation. Those pages will
\continue to be mainted by the documentation team, and will deep-link into
the project team documentation.

What is happening to each guide?
--------------------------------

* Installation Guide
  * Most of the content will move from openstack-manuals into each project
    tree.
  * The chapters not directly related to specific OpenStack projects, such as
    the parts related to installing ntp and RabbitMQ, will be retained in
    openstack-manuals in a new, pared down, "Before You Install" guide.
  * The current guide is actually built 3 separate times, to cover 3 separate
    deployment platforms. The new build will not support that, so the migration
    for the installation guide will involve breaking the content up into
    separate pages for each platform (as needed).
* Project Installation guides, already in tree
  * We recommend any installation guides already in-tree also move to the new
    organization.
* Administrator Guide
  * This content will move from openstack-manuals into each project tree. No
    part will be retained in openstack-manuals. This spec was already approved:
    https://review.openstack.org/#/c/439122/
* High Availability Guide
  * This guide will remain in openstack-manuals and be managed by the HA team.
    For more information: https://blueprints.launchpad.net/openstack-manuals/+spec/implement-ha-guide-todos
* Operations Guide
  * This guide will eventually move from openstack-manuals into the wiki.
    Nothing will be done with it until a volunteer is found to manage that move.
* Security Guide
  * This content will stay in openstack-manuals, and be managed by the security
    team.
  * A notice will be added to each page indicating the last time it was updated
    and which release is relevant.
* Architecture Design Guide
  * This content will stay in openstack-manuals, and be deprecated.
  * A notice will be added to each page indicating that the guide is up to date
    as of $RELEASE after the finalisation of the current set of goals. For more
    information on those goals:
    https://blueprints.launchpad.net/openstack-manuals/+spec/arch-design-pike
* Networking Guide
  * This content will move from openstack-manuals to the neutron repository
    under docs/source/admin.
* Configuration Reference
  * A few pages will move from openstack-manuals to the user-facing
    documentation in oslo.config.
  * The remainder will be removed, and replaced with new pages in the in-tree
    documentation built using oslo_config.sphinxext.
  * For tracking purposes, please see:
    https://blueprints.launchpad.net/openstack-manuals/+spec/automate-config-ref
* API Documentation
  * No changes, for now.
* End User Guide
  * This content will be divided between the horizon repository and
    python-openstackclient repository.
* Command-Line Reference
  * This content will move the project-specific client documentation trees under
    doc/source/cli
* Virtual Machine Image Reference
  * This content will stay in openstack-manuals.

Migration process
-----------------

We will need to parallelize the migration work as much as possible if we are
going to complete it by the end of the Pike cycle. We will therefore need
project teams to find volunteers to "pull" the content into their
repositories, instead of having the documentation team "push" it.

#. Pull in the content being migrated, following the layout above.
#. Move the existing contributor-focused content to fit the layout above.
#. Add auto-generated config reference section(s).
#. Update project-config to have the doc build use the new jobs instead of the
   old jobs by replacing 'openstack-server-publish-jobs' with
   'openstack-unified-publish-jobs'.
#. After the content and docs jobs for a repo are updated, set up the redirect
   from /developer to the new /contributor location.
#. After project-specific install guides are moved into the doc tree, set up
   the redirect from /project-install-guide to the new /install location.
#. Update the main landing page(s) starting with docs.o.o/ (see notes above)
#. Remove the original copy of the content from the openstack-manuals repo

   * This patch can be filed early with depends-on for the other related patches.

Alternatives
------------

#. We could retain the existing trees for developer and API docs, and add a new
   one for "user" documentation. The installation guide, configuration guide,
   and admin guide would move here for all projects. Neutron's user
   documentation would include the current networking guide as well. This option
   would add 1 new build to each repository, but would allow us to easily roll
   out the change with less disruption in the way the site is organized and
   published, so there would be less work in the short term.
#. We could move the content under separate repositories owned by the project
   teams, rather than in-tree with the code. This would allow project teams to
   delegate management of the documentation to a separate review
   project-sub-team, but would complicate the process of landing code and
   documentation updates together so that the docs are always up to date.
#. Do nothing, and watch the world burn.

We did consider using "service type" instead of "project name" for the
publishing URLs, but not all of the projects that need documentations
are services. We will have user-facing documentation coming from several
Oslo libraries, for example.

Implementation
~~~~~~~~~~~~~~

Assignee(s)
-----------

Primary assignee:

* Alexandra Settle (asettle)
* Doug Hellmann (dhellmann)
* Project teams
* Documentation team PTL for Queens
* Documentation team

Work items
----------

The task list is quite long, so rather than repeat it here we give a summary.
There is more detail in the tracking pad mentioned in step 3.

#. Define new doc build and gate jobs that work like the current job, using "tox
   -e venv -- python setup.py build_sphinx`" in a repository, but publish to the
   new location of docs.o.o/$project-name/latest
#. Define doc build jobs for stable branches that run the same command but
   publish to docs.o.o/$project-name/$series
#. In parallel, in each repository, perform the migration steps listed above to
   copy the new content into the doc/source directory. Refer to
   https://etherpad.openstack.org/p/doc-migration-tracking for details about
   which pages go into which project trees.
#. Define new translation jobs based on the ones for the release notes build but
   using the main doc build.

Dependencies
~~~~~~~~~~~~

- Project team(s) collaboration
- Infra team assistance
- Reviews from multiple sources

References
~~~~~~~~~~

* https://etherpad.openstack.org/p/doc-planning
* https://etherpad.openstack.org/p/doc-migration-tracking
* Documentation Publishing future thread: http://lists.openstack.org/pipermail/openstack-dev/2017-May/117162.html
* Operations Guide Future thread: http://lists.openstack.org/pipermail/openstack-dev/2017-June/117799.html
