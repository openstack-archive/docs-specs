..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============================
Removal of DocBook XML Support
==============================

https://blueprints.launchpad.net/openstack-manuals/+spec/docbook-removal

With the last conversions to RST done for the Newton cycle, we can
simplify our tools to only handle RST and thus remove DocBook XML support.

Problem description
===================

The tools support DocBook XML which is not needed for Newton deliverables.

Right now DocBook XML is used for:

* The ``trove`` repository.
* The ``api-site`` repository.
* The ``openstack-manuals`` repository on kilo and liberty stable
  branches.
* The ``operations-guide`` repository.

The operations-guide repository has one guide that is nearly finished
with RST conversion. The api-site repository contains the API
reference which is currently converted to RST. The trove repository
work has not started.

Proposed change
===============

Simplify all tools to only handle RST, remove support for DocBook XML.

Alternatives
------------

* Keep status quo.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  jaegerandi (Andreas Jaeger)

Work Items
----------

* Discuss with trove team the removal.
* For repositories that need XML publishing: Pin the
  openstack-doc-tools version to 0.34 since that is the last release
  with XML support.
* Convert glossary to RST and remove XML publishing from
  openstack-manuals repository.
* Remove DocBook XML publishing from openstack-doc-tools.
* Remove DocBook translation handling from openstack-doc-tools.
* Update contributor guide for this change.
* Update documentation in openstack-doc-tools for this change.


Dependencies
============

* None.


Testing
=======

* Testing of the tools will be done manually and as part of the
  builds. We should add some method to do integration testing.

References
==========

* https://etherpad.openstack.org/p/austin-docs-toolsinfra
