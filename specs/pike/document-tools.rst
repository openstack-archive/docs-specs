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

Update and complete the documentation for ``openstack-doc-tools`` and
``openstackdocstheme``, and consolidate it into a new **OpenStack Documentation
Tools Guide**. Add appropriate links to the new guide from the **OpenStack
Documentation Contributor Guide** and the repository README files.

Alternatives
------------

-  Consolidate the content into the existing **OpenStack Documentation
   Contributor Guide**
-  Create Sphinx documentation projects within the ``openstack-doc-tools`` and
   ``openstackdocstheme`` repositories, consolidate the content there, and
   publish the guides somewhere appropriate. Note that the
   ``openstack-doc-tools`` repository already has a Sphinx documentation
   project, but it mainly links to various README files and it is not published
   anywhere. ``openstackdocstheme`` also has a Sphinx documentation project
   that provides sample content for theme testing. This approach offers the
   benefit of using Sphinx extensions like auto-doc, but requires a location
   for publishing.
-  Maintain the status quo (do nothing)


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

-  Create a new **OpenStack Documentation Tools Guide** in the
   `openstack-manuals
   <http://git.openstack.org/cgit/openstack/openstack-manuals>`_ repository.
-  Copy existing content into the new guide.
-  Publish the new guide to docs.openstack.org.
-  Replace content in original locations with links to the content in the new
   guide.
-  Edit content and add missing material.


Dependencies
============

None


Testing
=======

Testing will follow the standard documentation review process.


References
==========

*  `openstack-doc-tools <http://git.openstack.org/cgit/openstack/openstack-doc-tools/>`_
*  `openstackdocstheme <http://git.openstack.org/cgit/openstack/openstackdocstheme/>`_
*  `openstack-manuals <http://git.openstack.org/cgit/openstack/openstack-manuals>`_
*  `OpenStack Documentation Contributor Guide <https://docs.openstack.org/contributor-guide/index.html>`_
