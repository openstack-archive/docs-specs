..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===================================================
Document openstack-doc-tools and openstackdocstheme
===================================================

https://blueprints.launchpad.net/openstack-doc-tools/+spec/document-tools


Problem description
===================

Documentation for `openstack-doc-tools
<http://git.openstack.org/cgit/openstack/openstack-doc-tools/>`_ and
`openstackdocstheme
<http://git.openstack.org/cgit/openstack/openstackdocstheme/>`_ is currently
divided between various README files in the project repositories and the
`OpenStack Documentation Contributor Guide
<https://docs.openstack.org/contributor-guide/index.html>`_. In some cases
content is duplicated, outdated, or missing.


Proposed change
===============

Create Sphinx documentation projects within the ``openstack-doc-tools`` and
``openstackdocstheme`` repositories, update and complete the documentation for
both repositories, then publish the guides to `docs.openstack.org/developer/
<https://docs.openstack.org/developer>`_.

Add appropriate links to the new guides from the **OpenStack Documentation
Contributor Guide** and the repository README files.

The ``openstack-doc-tools`` repository already has a Sphinx
documentation project that is not currently published but that can be used as
the basis for the guide.

``openstackdocstheme`` also has a Sphinx documentation project that provides
sample content for theme testing which should be retained or incorporated into
the published guide.


Alternatives
------------

-  Consolidate the content into a new **OpenStack Documentation Tools Guide**
   in the ``openstack-manuals`` repository.
-  Consolidate the content into the existing **OpenStack Documentation
   Contributor Guide**.
-  Maintain the status quo (do nothing).


Implementation
==============

Assignee(s)
-----------

Primary assignee:
   -  Brian Moss (bmoss)

Other contributors:
   -  Documentation team

Work Items
----------

-  Create Sphinx documentation projects within the ``openstack-doc-tools`` and
   ``openstackdocstheme`` repositories.
-  Copy existing content into the new guides.
-  Add doc checks to the tox environment and Jenkins gate.
-  Publish the new guides to docs.openstack.org/developer/$REPO.
-  Replace content in original locations with links to the content in the new
   guides.
-  Edit content and add missing material.


Dependencies
============

None


Testing
=======

Testing will follow the standard documentation review process.


References
==========

-  `openstack-doc-tools <http://git.openstack.org/cgit/openstack/openstack-doc-tools/>`_
-  `openstackdocstheme <http://git.openstack.org/cgit/openstack/openstackdocstheme/>`_
-  `openstack-manuals <http://git.openstack.org/cgit/openstack/openstack-manuals>`_
-  `OpenStack Documentation Contributor Guide <https://docs.openstack.org/contributor-guide/index.html>`_
