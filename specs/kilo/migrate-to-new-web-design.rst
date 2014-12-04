..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===========================
Migration to New Web Design
===========================

https://blueprints.launchpad.net/openstack-manuals/+spec/redesign-docs-site

We have a new web design that we've reviewed and vetted within the
documentation team. Here are the example pages:

* `Main page <http://openstack-homepage.bitballoon.com/docs>`_
* `Content view <http://openstack-homepage.bitballoon.com/docs/book>`_
* `Search results <http://openstack-homepage.bitballoon.com/docs/search>`_
* `Example language landing page <http://openstack-homepage.bitballoon.com/docs/ja>`_

We need to do some template and content migration work to get many docs onto
this new web design.

Problem description
===================

The problems with our current design for docs.openstack.org can be found in the
`Docs.OpenStack.org Redesign Project Brief
<https://docs.google.com/document/d/1GGKTKHDMc8A0jerdv-K3ql0udnxMr-j4DlhL2Cj6kcw/edit?usp=sharing>`_

The problem to solve with this blueprint specifically is getting the design
into Sphinx/jinja templates for use with RST source, as well as getting RST
source files from certain Docbook source files.

This is a phased approach to try to get many but not all docs migrated in the
Kilo release time frame.

Proposed change
===============

The User Guide, Admin User Guide, Cloud Administrator Guide, High Availability
Guide, API Quick Start Guide, and Virtual Machine Image Guide can all go to the
new design.

This new design will not apply to content that may remain as a book primarily,
and to limit the migration's scope to complete it in a timely way, this new
design would not apply to all deliverables. Examples of documents that will not
be migrated in the Kilo timeframe include the Install Guides, the Operations
Guide, the Security Guide, and the Architecture Design Guide. Those
deliverables will remain in Docbook and use the Maven plugin for builds for the
Kilo release.

Alternatives
------------

Rather than use RST/Sphinx for the new design, we could migrate to
markdown/Jekyll which is what the prototype design is already using. The
OpenStack ecosystem currently supports Python systems like Sphinx and
oslosphinx is available with a theme already.

We could get rid of Docbook completely for all books rather than the phased
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

Create jinja2 templates from Jekyll designs:
 - landing page
 - search page
 - content page

Update our build infrastructure so that sphinx is used for publishing

Test templates across browsers to ensure parity with design:
* Chrome on Ubuntu, Fedora, Mac, Windows
* Firefox on Ubuntu, Fedora, Mac, Windows

Update oslosphinx to have new openstack-docs theme:
Currently the theme name is "openstack." Reviewing the plan with Doug Hellman,
we can either keep the openstack theme and start one named "openstack-doc" or
update the openstack theme to be the new design. I prefer to name a new one
"openstack-doc" so that the current openstack theme which can indicate when a
project's doc is incubated remains.

Replace static www jinja templates in openstack-manuals with new design

Migrate Docbook to RST for these books in this priority order:
End User Guide
Admin User Guide
Cloud Administrator Guide
Virtual Machine Image Guide
High Availability Guide
API Quick Start Guide

Once migrated, apply new oslosphinx template to these repos and deliverables:
openstack-manuals:
* End User Guide
* Admin User Guide
* Cloud Administrator Guide
* Virtual Machine Image Guide
api-site:
* API Quick Start Guide
ha-guide:
* High Availability Guide

Remind projects to update their theme for /developer/ docs for:
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

Create a taxonomy for suggested tags as part of the `Conventions wiki page
<https://wiki.openstack.org/wiki/Documentation/Markup_conventions>`_
(klevenstein, loquacities)

Investigate how to publish PDF files within this new design.

Investigate how to ensure translation toolchain is supported with this new
design.

Investigate using index.rst collections across repos for new deliverable
assembly. This is not a required task for the migration, but will certainly
help with information architecture going forward towards "every page is page
one" rather than book-like deliverables. (jaegerandi)

Dependencies
============

* Foundation web developers hand-off of current design HTML and CSS files.
* Core olsosphinx reviewers helping with theme creation and reviews.

Testing
=======

We need to test the new design on these browsers/operating systems as a
priority:
* Chrome on Ubuntu, Fedora, Mac, Windows
* Firefox on Ubuntu, Fedora, Mac, Windows

References
==========

* https://docs.google.com/document/d/1GGKTKHDMc8A0jerdv-K3ql0udnxMr-j4DlhL2Cj6kcw/edit?usp=sharing

* https://etherpad.openstack.org/p/docstopicsparissummit

* https://wiki.openstack.org/wiki/Documentation/Markup_conventions
