..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Better share glossary across repositories
==========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/common-glossary-setup

Problem description
===================

Security-doc, operations-guide and openstack-manuals share the
glossary. We should only maintain it in one place and translate it in
one place. Right now, translations happen in any of these.

Proposed change
===============

The openstack-manuals repository should continue to be the master
source.

We need to evaluate what works best as implementation. We might be
able to import the glossary directly via http or need to have a copy
in each repository. And then figure out how to setup the repositories
that we can use the same translation files everywhere.

Alternatives
------------

Implementation
==============

Assignee(s)
-----------


Work Items
----------


Dependencies
============


Testing
=======


References
==========


