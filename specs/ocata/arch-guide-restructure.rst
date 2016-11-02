..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================================
Architecture Design Guide Restructure
=====================================

Problem description
===================

The current Architecture Design Guide is primarily organized by use case.
However, a combination of features from different use cases is often used when
designing an OpenStack cloud.

It is recommended to restructure content so the user can consider all the
requirements when designing an OpenStack cloud. Additional information should
be provided when designing an OpenStack cloud in a development, staged or
production environment. The proposal is to revise the content
structure to update use cases, but also create an abstraction between cloud
architecture concepts and various OpenStack projects. This will make it easier
to maintain the guide.

Proposed change
===============

The proposed structure of the guide is to first describe common cloud use
cases, then general architectural concepts, followed by cloud architecture
design with a detailed breakdown of the major cloud architecture components.

Proposed table of contents
--------------------------

The proposed structure for the updated Architecture Design Guide is as follows:

#. Overview
#. Use cases

   #. Development cloud
   #. General compute cloud
   #. Web scale cloud
   #. Public cloud
   #. Storage cloud
   #. Multi-site cloud
   #. Network Function Virtualization (NFV) cloud
   #. Specialized use cases

#. High Availability
#. Capacity planning and scaling

   #. Adding cloud controller nodes
   #. Segregating your cloud
   #. Scalable hardware

#. Design

   #. Compute

      *Implementation of the compute platform including
      hypervisors, nova, and ironic*

   #. Storage

      *Storage choices and the implementation of
      projects such as cinder and manila.*


   #. Networking

      *Networking design choices such as SDN, LBaaS,
      and neutron.*


   #. Identity

      *Authentication, authorisation, and assignment at
      all levels for keystone and related projects.*


   #. Image

      *Management, creation, distribution, and
      deployment of images for glance and related projects.*


   #. Control Plane

      *General implementation of the OpenStack control components and the
      decision making that goes into the choices that need to be made.*


   #. Dashboard and APIs

      *Interaction with cloud services using a graphical interface or the
      OpenStack APIs. This would include horizon and other Cloud Management
      Platform (CMP) tools.*


The section headings for each use case in the Use Cases chapter would be as
follows:

  #. Stakeholder
  #. User stories
  #. Design model
  #. Component block diagram

The sub-section headings in the Design chapter would be as follows:

  #. Technical detail
  #. Capacity and scale
  #. High availability
  #. Operator requirements
  #. Deployment considerations
  #. Maintenance considerations

The headings are intended as a guideline to the type of information that should
be provided. It will be used only when there is a specific need to provide
information.

Alternatives
------------

Leave the guide as is

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  * dazzachan

Other contributors:
  * shaunom
  * tersian
  * alexandra-settle

Work items
----------

* Migrate the Architecture chapter in the Operations Guide to the
  Architecture Design Guide
* Multiple contributors to write content
* Identify information gaps and submit patches

Dependencies
============

Contributions and input from cloud solution architects.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [arch-guide]
  in the subject, biweekly Ops Guide specialty team meeting,
  weekly documentation team meeting, and the Arch Guide working group meeting.

* `Draft Architecture Design Guide <http://docs.openstack.org/draft/arch-design-draft/>`_

* `Etherpad <https://etherpad.openstack.org/p/arch-guide-reorg-ocata>`_

.. _`Ops/arch tasks etherpad`: https://etherpad.openstack.org/p/ops-arch-tasks
