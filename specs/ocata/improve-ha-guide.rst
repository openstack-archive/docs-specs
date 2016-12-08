===================================
Improve the High Availability Guide
===================================

https://blueprints.launchpad.net/openstack-manuals/+spec/implement-ha-guide-todos

Problem description
===================

Presently, the High Availability (HA) Guide is incomplete. Information is sparse
and there are sections that have simply not been filled in.

The current guide is also out of date with regards to current best practices,
and it contains unnecessary information that should be removed.

Proposed change
===============

Firstly, reach consensus on the intended audience and high-level use cases
for the guide:

* As a cloud deployer, I need an OpenStack HA guide so that I can understand
  both the architectural principles behind building an HA OpenStack cloud,
  and the concrete steps involved in an implementation.

* As a cloud operator, I need an OpenStack HA guide so that I can understand
  how an existing HA OpenStack cloud works and what is required for its
  maintenance.

Based on that consensus, this spec proposes that the HA guide aims to define,
justify, and explain a high level architecture for a highly available setup
which uses the Pacemaker cluster manager to provide:

    * Detection and recovery of machine and application-level failures
    * Startup/shutdown ordering between applications
    * Preferences for other applications that must/must-not run on the same
      machine
    * Provably correct response to any failure or cluster state

The guide will aim to stay relevant across all distributions whilst not
attempting to give every tiny detail about how to implement HA for each
distribution. It will also aim to avoid duplicating too much
information which can be found elsewhere. For example, basic package
installation for a given distribution.

Since the existing guide already has plenty of helpful and relevant
information, the proposal for this guide aims to avoid any rip-and-replace
action preferring instead incremental change.

Andrew Beekhof (specialty team lead) proposes to use the following document
as a reference providing updated information for the improved guide:
https://github.com/beekhof/osp-ha-deploy/blob/master/ha-openstack.md

    .. note::

       The above Github document contains heavy Red Hat content. Some may be
       included in the final publication of the HA guide however it will be
       structured such that advocates of other distributions/tools will be
       able to easily add alternatives.

Alternatives
------------

* Leave the guide as is, and have the community slowly work at it over
  time.

* Retire the guide, move relevant information to other guides and archive
  it appropriately.

Implementation
==============

Assignee(s)
-----------

* Andrew Beekhof - beekhof
* Adam Spiers - aspiers
* Alexandra Settle - asettle

Work Items
----------
#. Go through HA guide bug list (see reference item 2) and remove what it out
   of date, and deal with any bugs that are relevant and current.

#. Go through HA guide and delete outdated or irrelevant information.

#. Rearchitect the guide for new structure.

#. Introduce new content based on the above Github document, and SME content.

Dependencies
============

* Potentially dependent on community engagement and SMEs providing content.

Testing
=======

This document will be tested by the community as it is updated.

References
==========

#. Mailing list discussion, December 2016: http://lists.openstack.org/pipermail/openstack-docs/2016-December/009410.html

#. Growing list of relevant bugs: https://bugs.launchpad.net/openstack-manuals/+bugs?field.tag=ha-guide
