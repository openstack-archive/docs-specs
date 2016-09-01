..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=============================================
Build PDF docs from rst-based guide documents
=============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/build-pdf-from-rst-guides

Generating PDF doc files for current openstack-manuals documents
and providing PDF download URLs to each HTML document is helpful for
users who want to see documents offline.

Problem description
===================

DocBook XMLs have been successfully migrated and converted
into RST sources. OpenStack RST-sourced documentation uses Sphinx
to build HTML documents and publish them on docs.openstack.org.
And openstackdocstheme is responsible for the theme and extension
in the published HTML documents.

One desired functionality in RST-sourced documents is to have PDF
versions of the books. Current HTML documents are surely helpful,
but having PDF versions provides OpenStack documentation readers
with more additional benefits. For example, users can download PDF files
and read them offline. To print HTML documents, users do more manual
steps such as moving from one page to other pages and the printed layout
is different from what users see through monitors. Furthermore,
it is easier for users to share their personal notes in PDF files with
other readers. One more advantage using PDF files is that PDF files have
pages. It is useful for offline training environment with printable
OpenStack documents by indicating page numbers.

Proposed change
===============

Add the support of building PDFs using current Sphinx build
infrastructure using RST-sourced files in openstack-manuals repository.

After Sphinx build supports PDF file generation, apply PDF buildings to
all the HTML documents in openstack-manuals repository, add the build
job to work with HTML builds, publish PDF files on docs.openstack.org
per each document build, and finally insert PDF download URLs
in the landing page of HTML documents.

Note that the main change will happen in openstack-doc-tools
for scripts, openstackdocstheme for possible additional themes for PDFs,
and each documentation repository such as openstack-manuals to add
PDF build support in Sphinx configurations.

Alternatives
------------

* Building PDFs seperately (without using current Sphinx build scripts)
  can be an alternative. However, this result will decrease the manageability
  of build scripts in documentation repositories.

* Document how users can built PDFs locally but do not publish PDFs.

* Leave the guide with current HTML build infrastructure as is.

Implementation
==============

Assignee(s)
-----------

* ianychoi
* jangpro2
* raymon-ha
* seungkyua
* sungjin

Work Items
----------

* Identifying requirements of libraries including rst2pdf
* Checking the compatibility of the libraries
* Changes in Sphinx configuration
* A basic PDF theme (fancy theme design is not the main goal)

  * Suggested minimums

    * title page
    * accurate page numbers
    * table of contents entries and links to H1, H2 from TOC
    * inline images are kept inside page print margins
    * tables wrap appropriately for page print margins
    * print target is standard size (e.g., 8.5x11 or A4)
    * grey or light color background for any code output for those
      who do print to save on ink/toner
    * open source font selections
    * file name does not contain spaces or special characters

* Integrating building PDF jobs with current tox HTML build environment
* Applying PDF build functionalities to all HTML documents in
  openstack-manuals repository

Project Scope
=============

* This spec mainly focuses on applying to documents in openstack-manuals
  repository. security-doc and api-site are also good targets for building
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

* Can be dependent on pdf build program (e.g., rst2pdf) version
  which is compatible with current Sphinx version for HTML builds

Testing
=======

* Testing of the tools will be done as part of the builds.
* Beta-reading period on PDF files and feedback will be helpful
  for checking layout problems such as less image resolution and
  table display problems.

References
==========

* http://lists.openstack.org/pipermail/openstack-docs/2016-July/008867.html
* http://lists.openstack.org/pipermail/openstack-docs/2016-July/008869.html
* rst2pdf: https://pypi.python.org/pypi/rst2pdf
