..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=========================================
OpenStack Documentation Contributor Guide
=========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/docs-contributor-guide


Problem description
===================

Based on the docs contributors experience and feedback, the information for
the documentation contributors located on wiki sometimes contains outdated
info and can be improved by restructuring and supplementing.

As we are treating our documentation as the code and willing others to do so,
we need to relocate all the conventions, how to instructions and any docs
contributor-related things to the place that fits as a single-entry, full,
and neatly organized guide that answers questions that arise in the docs
creation workflow.

The wiki is definitely not much convenient, it has narrowed functionality and
lacks a number of features that have become essential part of any internet user
nowadays, such as search, proper navigation, and some others.

Moving things around will noways influence its openness to the community or
make the conventions less flexible. This will only unify and simplify the
process.


Proposed change
===============

We propose the creation of the Documentation Contributors Guide
targeted at the contributors to the OpenStack documentation that will cover:

* Workflow (= Quickstart)

* Workflow (= HowTo)

* Licencing and copyrighting - an outline with links to:

  * http://www.openstack.org/brand/
  * https://review.openstack.org/static/cla.html
  * https://wiki.openstack.org/wiki/How_To_Contribute#Contributors_License_Agreement

* Markup conventions (RST - first priority, DocBook)

* Terminology and writing syntax conventions

* Screenshots and topologies conventions

* Documentation structure

* Team structure

Documentation Contributors Guide: RST

Here is the table that lists the existing wiki content and outlines how
it should be reworked from the contributor perspective:

.. list-table::
   :header-rows: 1

   * - Wiki page
     - User story

   * - `HowTo <https://wiki.openstack.org/wiki/Documentation/HowTo>`_

     - As a docs contributor, I would like to know in details: what tools are
       required; how to edit, check builds and commit the changes; how to amend
       a review-in-progress, cherry-pick and make changes to a stable branch;
       how to work with launchpad bugs and review patches.

   * - `HowTo/FirstTimers <https://wiki.openstack.org/wiki/Documentation/HowTo/FirstTimers>`_

     - As a docs contributor, I would like to have a quickstart guide with
       a suite of basic instructions on how to commit the change, respond
       to requests and troubleshoot.

   * - `Documentation/Builds <https://wiki.openstack.org/wiki/Documentation/Builds>`_
       and `Documentation/ContentSpecs <https://wiki.openstack.org/wiki/Documentation/ContentSpecs>`_

     - As a docs contributor, I would like to clearly understand what content
       goes where and where to get the sources (+ why the spec is required and
       how to create it)

   * - `Documentation/Conventions <https://wiki.openstack.org/wiki/Documentation/Conventions>`_

     - As a docs contributor, I would like to be aware of all the writing style
       guidelines that should be followed by the contributors to the OpenStack
       documentation.

   * - `Documentation/Markup_Conventions
       <https://wiki.openstack.org/wiki/Documentation/Markup_conventions>`_

     - As a docs contributor, I would like to be aware of all the XML/RST
       markup guidelines that should be followed by the contributors
       to the OpenStack documentation.

   * - `Documentation/JSON_Conventions <https://wiki.openstack.org/wiki/Documentation/JSON_conventions>`_

     - As a docs contributor, I would like to be aware of all the JSON
       guidelines that should be followed by the contributors to the OpenStack
       documentation.

   * - `Documentation/Structure <https://wiki.openstack.org/wiki/Documentation/Structure>`_

     - As a docs contributor, I would like to be aware of how to name and
       arrange files and directories in books.


.. note:: `HowTo <https://wiki.openstack.org/wiki/Documentation/HowTo>`_
   and `HowTo/FirstTimers <https://wiki.openstack.org/wiki/Documentation/HowTo/FirstTimers>`_ are also covered
   by http://docs.openstack.org/infra/manual/developers.html.
   We should not duplicate but reference to it there.


Implementation
==============

Work Items
----------

#. Create a seperate wiki page to keep all the related details on the
   project.

#. Work out the detailed and well-structured table of contents (on wiki).

#. Create, and adjust a separate directory in openstack-manuals for the guide.

#. Revise, move, and delete the existing (wiki) content.

#. Create new content, which is required from the contributor perspective,
   for example, Screenshots and topologies guidelines.

#. Make sure not to duplicate the content from
   http://docs.openstack.org/infra/manual/developers.html, but reference
   to it if it is required.

#. Add the link to the docs contribution workflow to the Infra Manual.


Assignee(s)
-----------

Primary assignee:
 Olga Gusarenko, `ogusarenko <https://launchpad.net/~ogusarenko>`_

Other contributors:

* Alexander Adamov, `aadamov <https://launchpad.net/~aadamov>`_

* Olena Logvinova, `ologvinova <https://launchpad.net/~ologvinova>`_

* Maria Zlatkova, `mzlatkova <https://launchpad.net/~mzlatkova>`_

.. TODO: please, let me know if you are interested in participating, and I will
   add you to the list


Testing
=======

Feedback from the docs contributors


References
==========

* Add the link to the project wiki page.
