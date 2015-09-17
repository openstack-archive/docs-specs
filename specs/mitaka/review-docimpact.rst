..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

================
Review DocImpact
================

https://blueprints.launchpad.net/openstack-manuals/+spec/review-docimpact

The ``DocImpact`` script creates a lot of noise on the openstack-manuals bug
list. This is partly a social problem (we need to train contributors to use
the ``DocImpact`` flag more thoughtfully), but also partly an automation
problem (we should be considering how the ``DocImpact`` flag is used, and the
most efficient automation to achieve the end we require.

Problem description
===================

Current workflow: Contributors create a patch, and at commit time they think
"oh yeah, probably there should be some docs about that" and whack in a
``DocImpact`` flag. In other words, there's not a lot of thought going in
here, it's just an easy thing to do, they get a warm fuzzy, and there's an
assumption that the documentation fairy comes along and takes care of things.
In reality, what then happens is some docs triager spends an hour looking at
the patch, searching through the docs, then deciding it has nothing to do with
openstack-manuals. Often, the actual doc impact (if there even is one) is
against docs in the dev repo, not openstack-manuals.

In short, contributors recognise they need docs, and ``DocImpact`` is an easy
way to feel like they're doing something productive to make that happen. What
really happens is that those bugs are largely irrelevant for
openstack-manuals, which puts pressure on our core team to triage them
effectively. To try and get some perspective on the size of the problem, here
are some numbers:

Of the 508 current openstack-manuals bugs, 214 are the result of the DocImpact
script. 51 of these are yet to be triaged. Right now, there are 170 patches
in-flight with the DocImpact tag. To state the obvious, if all them land,
that's 170 new bugs in our queue.

Proposed change
===============

* Adjust ``DocImpact`` so that it cannot be used without a description.
  Currently, that is an optional thing contributors can do, but it appears
  that no one uses it. This would mean that rather than typing "DocImpact" and
  moving on with their lives, contributors must write "DocImpact: Something
  relevant here".

* A Jenkins job is used to test for the description field in patches. If no
  description field is found, the Jenkins job will fail.

* Currently, all projects default to create a bug in the openstack-manauals
  queue. This behaviour will be changed so that all projects default
  to raising a bug in their own repo, and only the five defcore projects
  (Nova, Swift, Glance, Keystone, and Cinder) go to the openstack-manuals
  queue. (Neutron to be added once it becomes defcore, planned for 2016).

* Create an education campaign on the dev mailing list, and possibly other
  channels, in order to try and encourage contributors to use the flag
  responsibly.

Examples
--------

Some examples of correct ``DocImpact`` usage:

* Where the documentation needs to be updated:

.. code-block: ini

   DocImpact: Update in the Networking section of the Ubuntu Install Guide

* The type of documentation required:

.. code-block: ini

   DocImpact: Add a description and install info for $NEW_FEATURE.

* Changes to existing documentation:

.. code-block: ini

   DocImpact: Current docs say X, should be Y.

* Link to a longer piece of documentation (such as OpenStack pastebin,
etherpad, or a blog post):

.. code-block: ini

   DocImpact: For more info, see http://paste.openstack.org/show/479077/


Alternatives
------------

* Have a crack team of docs people (potentially with automation
  assistance) going through ``DocImpact`` bugs, cc'ing the original patch
  authors, triaging the valid ones, moving others into dev repos where
  necessary, and marking the rest invalid. We could team this with an
  education campaign on the dev mailing list.

* Ditch ``DocImpact``, and force contributors to create their own docs bugs
  (and patches). This would mean fewer contributors get on with the job of
  documentation, but at least what we do get would be well-considered, rather
  than hastily added to their commit message.

* ``DocImpact`` doesn't log a bug at all but rather indicates that the patch
  contains docs. This style of commit message then aligns with APIImpact,
  where the API Working Group reviews incoming patches with that tag. This
  won't work currently, as we don't have a good mechanism for searching for
  the flag (the current docs dashboard doesn't do this).

* Do nothing. Leave the ``DocImpact`` flag the way it is, and slowly drown.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* Lana Brindley (loquacities)

Other contributors:

* Documentation team
* Infra team

Work Items
----------

* Enforce a description field on the DocImpact flag. (Infra)

* Review the projects that can raise DocImpact flags in the openstack-manuals
  queue. (AJaeger)

* Plan and implement an education campaign. (loquacities)

References
==========

* https://lists.launchpad.net/openstack-doc-core/msg00286.html

