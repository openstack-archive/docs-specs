..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=========================================
Config Reference: document common options
=========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/config-ref-common-sections

Problem description
===================

In the configuration reference, configuration options such as database,
AMQP, keystone middleware are poorly documented, or worse, documented
differently in multiple places.

This might be confusing for the reader, and adds maintenance burden.

Proposed change
===============

Common libraries define several configuration options, used by all the
OpenStack projects. Instead of documenting these options for each project,
we could have a specific chapter documenting the configuration options for
common libraries, and refer to this chapter in the projects chapters.

At the moment these options are poorly documented, so this change would also be
a chance to add missing information, or at least provide a better structure to
do so in the future.

This spec only impacts the configuration reference.


Alternatives
------------

* Document everything in all the projects chapters, leading to a lot of
  duplication

Implementation
==============


Assignee(s)
-----------

Primary assignee: gpocentek


Work Items
----------

* Generate options tables using ``autohelp`` for the common libraries. The
  options would not be removed from the projects tables, to keep providing a
  complete set of options for each project.

* Add a new ``Common configuration options`` chapter to the configuration
  reference, documenting configuration options available in ``oslo`` and
  ``keystonemiddleware`` libraries. Documented libraries include
  (non-exhaustive list):

  * ``oslo.concurrency``
  * ``oslo.db``
  * ``oslo.log``
  * ``oslo.messaging``
  * ``keystonemiddleware.auth_token``

* Remove documentation for these options in the projects chapters, if necessary
  (AMQP with ``oslo.messaging`` is sometimes documented).

* In each component chapter, add references to the common options sections.


Dependencies
============

None

Testing
=======

* Validate the existence of documented options using the tables generated with
  ``autohelp``.

References
==========

None
