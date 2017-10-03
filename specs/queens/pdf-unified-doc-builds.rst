..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

======================================================
PDFs for project-specific docs with unified doc builds
======================================================

https://blueprints.launchpad.net/openstack-manuals/+spec/pdf-unified-doc-builds

Supporting PDF doc files for project-specific OpenStack documents is
helpful for users who want to see the documents offline.

Problem description
===================

OpenStack RST-sourced documentation uses Sphinx to build HTML documents
and publish them on docs.openstack.org. RST-sourced documents in
openstack-manuals also have PDF versions of the books.
It will be helpful if the PDF versions of the books is extended to
all OpenStack project-specific docs.

Proposed change
===============

Add the support of building PDFs into unified doc builds job.

Alternatives
------------

* Building PDFs separately (without using current Sphinx build scripts)
  can be an alternative. However, this result will decrease the manageability
  of build scripts in documentation repositories.

* Document how users can built PDFs locally but do not publish PDFs.

* Leave the guide with current HTML build infrastructure as is.

Implementation
==============

Assignee(s)
-----------

* ianychoi
* chason
* jang0913
* nexusz99

Work Items
----------

* Test Sphinx builder with setup.cfg

    * http://www.sphinx-doc.org/en/stable/setuptools.html#confval-builder

* Applying to PDF support in one official project as an example

    * conf.py modification

* Changes on unified doc build scripts

    * Also using latex builder
    * "make" command to convert from latex to pdf
    * Finding a pdf file name
    * Copying the pdf file to publish folder
    * Applying binary dependency (bindep.txt) in infra

Project Scope
=============

* This spec mainly focuses on applying to project-specific repository
  documents by extending the method of building PDFs in openstack-manuals.
* security-doc and api-site are also good targets for building
  PDFs, but they are out of scope in this spec.
* The support of building PDFs from translated documents is out of scope.
* For a basic PDF theme, the following requirements are out of scope.

    * Index with page numbers
    * OpenStack logo display on title page
      (choosing which logo is appropriate for each deliverable would
      get tedious)
    * Optional: watermark to indicate draft or to which version
      the document applies

Dependencies
============

* Can be dependent on PDF build support functionalities in Sphinx

Testing
=======

* Testing of the tools will be done as part of the builds.

References
==========

* http://specs.openstack.org/openstack/docs-specs/specs/ocata/build-pdf-from-rst-guides.html
* http://lists.openstack.org/pipermail/openstack-dev/2017-September/122603.html
* https://review.openstack.org/#/c/520620/1
