..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

======================================
Add documentation about heat templates
======================================


Problem description
===================

The documentation about how to write heat templates in the openstack-manuals
repository is almost nonexistent. The developer resources are a good starting
point, but don't provide enough information to easily learn how to write
templates.


Proposed change
===============

The proposed change is to add a chapter in the user guide.

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


Alternatives
------------

Implementation
==============

The documentation will initially be written in RST, to ease developers
contributions. A tool to convert RST to docbook will be provided.

The template reference provided in the heat repository will be converted to
docbook and imported in an existing guide, or in a dedicated guide (to be
decided later).

Assignee(s)
-----------

Gauvain Pocentek (gpocentek)

Work Items
----------

* Write the RST to docbook conversion tool
* Write the doc in RST
* Import the result of the conversion in the user guide when ready
* (Maybe) Automate the import for future updates

Dependencies
============


Testing
=======


References
==========

* https://github.com/openstack/heat/tree/master/doc/source/template_guide
* http://docs.openstack.org/developer/heat/template_guide/openstack.html
