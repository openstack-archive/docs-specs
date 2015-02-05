..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===========================
Migration to New Web Design
===========================

https://blueprints.launchpad.net/openstack-manuals/+spec/redesign-docs-site

The documentation team has reviewed and vetted a new web design. Here are the
example pages:

* `Main page <http://openstack-homepage.bitballoon.com/docs>`_
* `Content view <http://openstack-homepage.bitballoon.com/docs/book>`_
* `Search results <http://openstack-homepage.bitballoon.com/docs/search>`_
* `Example language landing page <http://openstack-homepage.bitballoon.com/docs/ja>`_

This blueprint describes the steps required to implement this new web design.

Problem description
===================

In brief, we have design problems that are addressed with the new design. The
problem to solve is how to get many documents to use the new design.

A related relevant document is the
`Docs.OpenStack.org Redesign Project Brief
<https://docs.google.com/document/d/1GGKTKHDMc8A0jerdv-K3ql0udnxMr-j4DlhL2Cj6kcw/edit?usp=sharing>`_ which describes the many problems with the current design.

The problem to solve with this blueprint specifically is getting the design
into Sphinx/jinja templates for use with RST source, as well as getting RST
source files from certain DocBook source files.

This is a phased approach to try to get many but not all docs migrated in the
Kilo release time frame.

Proposed change
===============

In the Kilo time frame, migrate these books to the new design:

* End User Guide
* Admin User Guide

As time permits, continue to migrate these books to the new design:

* Cloud Administrator Guide
* High Availability Guide
* API Quick Start Guide
* Virtual Machine Image Guide

To limit the scope of the migration, these books will not be migrated:

* Install Guides
* Operations Guide
* Security Guide
* Architecture Design Guide

These deliverables will remain in DocBook and use the Maven plugin for builds
for the Kilo release.

Alternatives
------------

Rather than use RST/Sphinx for the new design, we could migrate to
markdown/Jekyll which is what the prototype design is already using. The
OpenStack ecosystem currently supports Python systems like Sphinx and
oslosphinx is available with a theme already.

We could get rid of DocBook completely for all books rather than the phased
approach. I don't think that we have the time to do that in a six-month
release, so I'm proposing a phased approach.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  annegentle

Other contributors:
  jagerandi
  loquacities
  klevenstein
  dhellman

Work Items
----------

Research:

January 2015
- Investigate how to publish PDF files within this new design.
- Investigate using index.rst collections across repos for new deliverable
assembly. This is not a required task for the migration, but will certainly
help with information architecture going forward towards "every page is page
one" rather than book-like deliverables. (jaegerandi)

Frameworks:

January: Create a taxonomy for suggested tags as part of the `Conventions wiki
page
<https://wiki.openstack.org/wiki/Documentation/Markup_conventions>`_
(klevenstein, loquacities)

DONE January 15, 2015: Create jinja2 templates from Jekyll designs for:

* landing page and search (fifieldt)

DONE February 20, 2015: Create Sphinx template from Jekyll design for:

* content pages (annegentle)

DONE February: Replace static www jinja templates in openstack-manuals with
new design

Proof of concept with content:

February 15, 2015: Migrate DocBook to RST for these books in this priority
order:

* End User Guide
* Admin User Guide

Tracking on wiki page: https://wiki.openstack.org/wiki/Documentation/Migrate

February 28, 2015: Update our build infrastructure
so that Sphinx is used for publishing these documents:

* End User Guide
* Admin User Guide

February 20, 2015: Test templates across browsers to ensure parity with design:

* Chrome on Ubuntu, Fedora, Mac, Windows
* Firefox on Ubuntu, Fedora, Mac, Windows

March 2015: Test translation toolchain. Ying Chun Guo (Daisy) has agreed to
investigate.

DONE February 15, 2015: Update oslosphinx to have new openstackdocs theme:
Currently the theme name is "openstack." Reviewing the plan with Doug Hellman,
we can either keep the openstack theme and start one named "openstackdocs" or
update the openstack theme to be the new design. I prefer to name a new one
"openstackdocs" so that the current openstack theme which can indicate when a
project's doc is incubated remains.

DONE Updated to add: looking at the information architecture of the header,
it looks like it's best to have an openstack docs theme that doesn't
necessarily live in oslosphinx. Oslosphinx is used for
http://specs.openstack.org, http://ci.openstack.org,
http://governance.openstack.org for example, and
http://ci.openstack.org has modified the header so that it wouldn't
match the other sites. As a result, the plan is to keep the oslosphinx
theme with oslosphinx and create a theme in a separate repo named
openstackdocsthemes for application to all content published to
http://docs.openstack.org.

March (after proof-of-concept and CI is complete): Migrate DocBook to RST for
these books in this priority order:

* Cloud Administrator Guide
* Virtual Machine Image Guide
* High Availability Guide
* API Quick Start Guide

March: Once migrated, apply new openstackdocstheme template to these repos and
deliverables:

openstack-manuals:

* End User Guide
* Admin User Guide
* Cloud Administrator Guide
* Virtual Machine Image Guide

api-site:

* API Quick Start Guide

ha-guide:

* High Availability Guide

March: Remind projects to update their theme for /developer/ docs for:

 * nova
 * neutron
 * glance
 * keystone
 * ceilometer
 * cinder
 * heat
 * horizon
 * ironic
 * sahara
 * swift
 * trove

Dependencies
============

Foundation web developers hand-off of current design HTML and CSS files.
(Done)

Core olsosphinx reviewers helping with theme creation and reviews. (Done)

Translation team investigate and test translation toolchain.

Testing
=======

We need to test the new HTML design on these browsers/operating systems as a
priority:

* Chrome on Ubuntu, Fedora, Mac, Windows
* Firefox on Ubuntu, Fedora, Mac, Windows

Need to test translation toolchain.

Need to test PDF output if it's possible to get.

References
==========

* https://docs.google.com/document/d/1GGKTKHDMc8A0jerdv-K3ql0udnxMr-j4DlhL2Cj6kcw/edit?usp=sharing

* https://etherpad.openstack.org/p/docstopicsparissummit

* https://wiki.openstack.org/wiki/Documentation/Markup_conventions

* http://idratherbewriting.com/2012/12/04/what-does-every-page-is-page-one-and-include-it-all-filter-it-afterward-mean/
