..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================================
Architecture Design Guide Restructure
=====================================

Problem description
===================

The current Architecture Design Guide is primarily organized by use case
resulting in duplication of cloud architecture concepts.

The proposal is to revise the content structure to refine use cases to the
most common OpenStack deployments, and create an abstraction between
cloud architecture concepts and various OpenStack projects. This will make it
easier to maintain the guide.

Proposed change
===============

The proposed structure of the guide is to first describe common cloud use
cases, then general architectural concepts, followed by cloud architecture
design with a detailed breakdown of the major cloud components.

Proposed table of contents
--------------------------

The proposed structure for the updated Architecture Design Guide is as follows:

#. Overview
#. Use cases

   #. Development cloud
   #. General compute cloud
   #. Web scale cloud
   #. Storage cloud
   #. Network Function Virtualization (NFV) cloud

#. High Availability

   *Business requirements for implementing HA, what components in the
   control plane need to be HA and why.*

#. Capacity planning and scaling

   #. Adding cloud controller nodes
   #. Segregating your cloud
   #. Scalable hardware

#. Design

   #. Compute

      *Implementation of the compute platform including
      hypervisors, nova, and ironic.*

   #. Storage

      *Storage choices and the implementation of
      projects such as cinder and manila.*


   #. Networking

      *Networking design choices such as SDN, LBaaS,
      and neutron.*


   #. Identity

      *Authentication, authorization, and assignment at
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


The Use cases chapter will document the five most common OpenStack use cases.
It will describe the scope and requirements, which will be a precursor for
reference architecture information.

The sub-section headings in the Design chapter would be as follows:

  #. Technical detail
  #. Capacity and scale
  #. High availability
  #. Operator requirements
  #. Deployment considerations
  #. Maintenance considerations

The sub-section headings are intended as a general guideline to the type of
information that should be provided. It will be used when there is a specific
need to provide information.

Alternatives
------------

Leave the guide as is.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  * dazzachan

Other contributors:
  * tersian
  * alexandra-settle

Work items
----------

* Remove the current Architecture Design Guide from docs.openstack.org, and
  publish the draft Architecture Design Guide in its current state to
  to increase visibility.
* Remove the Architecture chapter from the Operations Guide since the content
  has been migrated to the draft Architecture Design Guide.
* Update ``.htaccess`` with redirects for removed/changed URLs.
* Complete writing the storage and networking sections in the
  Design chapter, followed by the remaining sections.
* For each task, submit a bug report.
* Develop a use case content template to be applied to the Use Cases chapter.

Dependencies
============

Contributions and input from SMEs.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [arch-guide]
  in the subject heading, and `biweekly documentation team meeting
  <https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting>`_.

* `Draft Architecture Design Guide <http://docs.openstack.org/draft/arch-design-draft/>`_

* `Work items <https://wiki.openstack.org/wiki/Architecture_Design_Guide_restructure_work_items>`_
