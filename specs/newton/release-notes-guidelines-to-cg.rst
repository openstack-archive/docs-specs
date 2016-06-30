..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================
Release notes guidelines
========================

https://blueprints.launchpad.net/openstack-manuals/+spec/release-notes-guidelines-to-cg

To maintain the overall quality of the OpenStack documentation,
the release notes guidelines should be developed and published.

Problem description
===================

As a developer who creates the release notes for the OpenStack project
I contribute to, I would like to have clear and concise writing style
guidelines for the release notes as well as a handy list of all
sources of information regarding the release notes management within
the project.

Proposed change
===============

The proposed changed is to add the following information to the Contributor
guide:

* Release notes sections, what include where
* Writing style guidelines (verb forms, sentence structures, links inclusion,
  etc.)
* Release notes *bad -> improved* examples
* Reno overview for general understanding of how things work there.
* The list of rn-related links shaped in a form what-find-where.

Alternatives
------------

We can add these recommendations to the `Project Team guide <http://docs.openstack.org/project-team-guide/release-management.html>`_,
`Infra manual <http://docs.openstack.org/infra/manual/developers.html>`_,
or `Reno documentation <http://docs.openstack.org/developer/reno/>`_.

Despite of the fact that these locations may fit (mainly because
they are targeted at developers who create release notes for projects),
there are strong arguments in favor of the Contributor guide, and they are
as follows:

* *Project Team guide* mostly refers to procedures rather than to wording.

* *Infra manual* contains only general workflow of contributing to
  OpenStack source code repositories rather than specific use-cases such as
  the release notes creation.

* *Reno documentation* - though it is fully dedicated to the release notes
  creation process and shaped for the developers (our main intended audience),
  this is just a tool that can be replaced in future with another release
  notes management tool with its own documentation.

To sum up, Contributor guide still remains the best place to document
release notes style guidelines and to put together all sources of truth
for the release notes creation.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Olga Gusarenko <ogusarenko>

Work Items
----------

The work items include the following:

* Create the overview of Release notes sections, what include where.

* Develop the writing style guidelines (verb forms, sentence structures,
  links inclusion, etc.).

* Make up bad examples of release notes and rework them.
  Present them in a form of *bad -> improved* examples for better illustration.

* Create Reno overview for general understanding of how things work there and
  why Community uses it to manage release notes.

* Make a list of rn-related links in a form what-find-where.

* Add a reference to the Contributor Guide
  at `Project Team guide <http://docs.openstack.org/project-team-guide/release-management.html#how-to-add-new-release-notes>`_.

Dependencies
============

n/a

Testing
=======

n/a

References
==========

* `Contributor Guide Austin Session notes <https://etherpad.openstack.org/p/austin-docs-contributorguide>`_.
* `Reno documentation <http://docs.openstack.org/developer/reno/>`_.
* Current instructions for the developers
  `Managing Release Notes <http://docs.openstack.org/project-team-guide/release-management.html#how-to-add-new-release-notes>`_.
