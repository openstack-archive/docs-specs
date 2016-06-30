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
sources of information regarding release notes management within
the project.

Proposed change
===============

The proposed change is to add the following information to the Contributor
guide:

* Release notes sections, what is included where
* Writing style guidelines (verb forms, sentence structures, links inclusion,
  etc.)
* Release notes *bad -> improved* examples
* Reno overview for general understanding of how things work there.
* The list of links where different pieces of release notes related
  information can be found (Reno docs, project team guide, etc).

Alternatives
------------

We can add these recommendations to the `Project Team guide <http://docs.openstack.org/project-team-guide/release-management.html>`_,
`Infra manual <http://docs.openstack.org/infra/manual/developers.html>`_,
or `Reno documentation <http://docs.openstack.org/developer/reno/>`_.

Despite of the fact that these locations may fit (mainly because
they are targeted at developers who create release notes for projects),
there are strong arguments in favor of the Contributor guide:

* *Project Team guide* mostly discusses adjusting a project's repo
  to use the release management tool rather than to release notes writing
  style.

* *Infra manual* contains only general workflow of contributing to
  OpenStack source code repositories rather than specific use-cases such as
  the release notes creation.

* *Reno documentation* - though it is fully dedicated to the release notes
  creation process and shaped for the developers (our main intended audience),
  this is just a tool that can be replaced in future with another release
  notes management tool with its own documentation.

To sum up, Contributor guide still remains the best place to document
release notes writing style guidelines for a number of reasons:

* Release notes are part of documentation
* Contributor guide`s intended audience is documentation contributors.

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

* Develop the writing style guidelines (release notes specific).
  These include:

  * Verb forms
  * Sentence structures for different types of release notes (New features,
    Bug fixes, etc.)
  * Links inclusion

* Make up bad examples of release notes and rework them.
  Present them in a form of *bad -> improved* examples for better illustration.

* Create Reno overview for general understanding of how things work there and
  why Community uses it to manage release notes.

* Create subsection ("Additional resources") that lists links, where different
  pieces of release notes related information can be found, with brief
  descriptions.

* Cross-references:

  * `Project Team guide <http://docs.openstack.org/project-team-guide/release-management.html#how-to-add-new-release-notes>`__
  * `Reno documentation <http://docs.openstack.org/developer/reno/>`_
  * `Infra manual <http://docs.openstack.org/infra/manual/developers.html>`_

* Inform OpenStack developers about the release notes guidelines when
  published:

  * Through the openstack-dev mailing list
  * Add the release note to documentation release notes for Newton

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
