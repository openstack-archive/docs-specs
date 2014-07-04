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

The repositories security-doc, operations-guide, and openstack-manuals
share the glossary. In the future the training-guides repository might
use it as well. We should only maintain it in one place.

Also, translation should be only done in one place. Right now,
translations happen in any of these repositories: In openstack-manuals
using a separate POT file, in security-doc and operations-guide as
part of the books.

Currently, the glossary is manually imported in the operations-guide
and security-doc repositories when necessary. The operations-guide
even contains a slightly different header than the version in the
openstack-manuals repository.

The glossary terms must be available to maven at build time to ensure
the links all work correctly.

Proposed change
===============

We should continue to have a master source glossary.

The openstack-manuals repository should continue to be the master
source.

Once a change to the glossary in the master source happens, it will be
proposed to the other repositories via a Jenkins job.

Alternatives
------------

* Using a separate glossary repository and using git submodules in the
  other repositories.

* Another option would be to checkout the repository containing the
  glossary and its translation at a well-known location at build
  time. This would require that every user locally building needs to
  have the same setup.

* Another alternative may be to create a new openstack/glossary
  repository and always copy from there, rather than having
  openstack/openstack-manuals/doc/glossary be the storing place.
  Raising the level to a repo may help get more contributions to the
  glossary.


Implementation
==============

Assignee(s)
-----------

Andreas Jaeger (jaegerandi)


Work Items
----------

* Move files as needed.
* Test solution manually for Security Guide and Operations Guide.
* Change build jobs as needed.


Dependencies
============


Testing
=======


References
==========
