..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

======================================
Add documentation about heat templates
======================================

https://blueprints.launchpad.net/openstack-manuals/+spec/heat-templates

Problem description
===================

The documentation about how to write heat templates in the openstack-manuals
repository is almost nonexistent. The developer resources are a good starting
point, but don't provide enough information to easily learn how to write
meaningful templates.

The HOT reference (properties and attributes of resources, available functions,
...) is published only for the current development branch, from the heat
documentation (in the developer/ section of the published documentation). This
reference should be available for users along the other references (config
reference, CLI reference), for each released version of heat.


Proposed change
===============

Two changes are proposed:

* Adding a chapter to the user guide
* Providing a new guide: "Heat Orchestration Templates (HOT) Reference Guide"

Adding a chapter to the user guide
----------------------------------

A first section would cover the basic aspects of templates:

* Architecture, format and languages
* Resources definition
* Parameters definition
* Usage of functions and attributes
* Links between resources

This section would cover the base resources: nova server, neutron nets, subnets
and ports, cinder volumes

A second section will document how to use more complex resources such as:

* WaitConditions
* HA and alarming
* AutoScaling

Providing a new guide: the HOT reference
----------------------------------------

This guide will be automatically built from the heat source code and
documentation.

Alternatives
------------

Some alternatives we considered and discuss on the mailing list previously
include:

* Starting a new standalone guide for Templates within openstack-manuals,
  sourced in DocBook. We decided the overhead for a new non-automated guide was
  too much, and end users are going to want to know this exists.

* Convert the entire End User Guide from DocBook to RST and build with Sphinx,
  using the oslosphinx tempate for output. We would lose the translation
  toolchain and the PDF from this output chain is not as nice as the DocBook
  PDF.

So, to take the best of both tool chains, this proposal chooses to create a
chapter in the End User Guide, ultimately in DocBook, but through an RST path.


Implementation
==============

The documentation will initially be written in RST, to ease developers
contributions. A tool to convert RST to DocBook will be provided.

The template reference provided in the heat repository will be converted to
DocBook and imported in an dedicated guide.

Assignee(s)
-----------

Gauvain Pocentek (gpocentek)

Work Items
----------

* Write the RST to DocBook conversion tool.
* Write the doc in RST.
* Import the result of the conversion in the user guide when ready.
* (Maybe) Automate the import for future updates.
* Automatically publish the reference information for heat templates in a
  separate guide.

Dependencies
============


Testing
=======

Minimalistic but functional templates will be provided along the guide. Default
values for parameters will be set to easily work on a devstack environment.
This should ease the testing.

These templates could be provided as part of the `heat-templates repository`_.

.. _`heat-templates repository`: https://github.com/openstack/heat-templates

References
==========

* https://github.com/openstack/heat/tree/master/doc/source/template_guide
* https://github.com/openstack/heat-templates
* http://docs.openstack.org/developer/heat/template_guide/openstack.html
