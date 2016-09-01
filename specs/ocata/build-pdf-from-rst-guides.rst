..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=============================================
Build PDF docs from rst-based guide documents
=============================================

Include the URL of your launchpad blueprint:

https://blueprints.launchpad.net/openstack-manuals/+spec/build-pdf-from-rst-guides

Generating PDF doc files for current openstack-manuals documents
and providing PDF download URLs to each HTML document is helpful for
users who want to see documents in offline.

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
and read them in offline. To print HTML documents, users do more manual
steps such as moving from one page to other pages and the printed layout
is different from what users see through monitors. Furthermore,
it is easier for users to share their personal notes in PDF files with
other readers. One more advantage using PDF files is that PDF files have
pages. For instance, users can say "Please see page X in the PDF file"
instead of pointing out such as "Browse the HTML document, click section A
and B, and find topic C".

Proposed change
===============

Add the support of building PDFs using current Sphinx build
infrastructure using RST-sourced files in openstack-manuals repository.

After Sphinx build supports PDF file generation, apply PDF buildings to
all the HTML documents in openstack-manuals repository, add the build
job to work with HTML builds, publish PDF files on docs.openstack.org,
and finally insert PDF download URLs in HTML documents.

Alternatives
------------

If adding build jobs into openstack-infra is difficult due to such as
installation fails with package depencencies, building PDF files
in offline, uploading them into docs.openstack.org and insert download
links in HTML documents would be possible alternative approach.

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
* Checking tex library support (installation & compatibility) in current
  Sphinx building jobs
* Changes in Sphinx configuration
* A basic PDF theme (fancy theme design is not the main goal)
* tox environment for building PDF files
* openstack-infra build job to generate and publish PDF files
* Applying PDF build functionalities to all HTML documents in
  openstack-manuals repository
* (future) support of building PDFs from translated documents

Dependencies
============

* pdf build program (e.g., rst2pdf) installation fails with
  package depencencies in openstack-infra

Testing
=======

* Testing of the tools will be done manually and as part of the
  builds. We should add some method to do integration testing.

References
==========

* http://lists.openstack.org/pipermail/openstack-docs/2016-July/008867.html
* http://lists.openstack.org/pipermail/openstack-docs/2016-July/008869.html
* rst2pdf: https://pypi.python.org/pypi/rst2pdf
