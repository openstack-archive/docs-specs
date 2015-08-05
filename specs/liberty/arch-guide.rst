..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

======================================
Architecture Design Guide Improvements
======================================

https://blueprints.launchpad.net/openstack-manuals/+spec/arch-guide

Review, edit, and reorganize the Architecture Design Guide.


Problem description
===================

The Architecture Design Guide has not been thoroughly reviewed since its
creation. This has led to the following issues:

- language and syntax not in accordance with our conventions
- improvable information architecture
- duplication of content


Proposed change
===============

- Reorganize guides to improve presentation of existing content
- Clean up existing content where necessary and remove duplication
- Identify information gaps and raise bugs where necessary

This work is a precursor to converting this guide from Docbook XML to RST in a
future release.

Alternatives
------------

- Leave the guide as it is
- raise bugs against each individual section that requires improvement

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Brian Moss (bmoss)

Other contributors:
  Documentation Swarm attendees


Work Items
----------

The bulk of this work is expected to be completed at the upcoming documentation
swarm taking place in Brisbane AU on August 13-14. See :ref:`References`.

- Rework the abstract to clearly identify the audience and purpose of the book
- Reduce duplication in the guide as much as possible.
- Edit for consistency and adherence to our conventions
- Move sections as required to improve information architecture

Dependencies
============

None

Testing
=======

Standard documentation review process.

.. _References:

References
==========

`Documentation Conventions <https://wiki.openstack.org/wiki/Documentation/Conventions>`_

`Swarm Website <http://openstack-swarm.rhcloud.com/>`_
