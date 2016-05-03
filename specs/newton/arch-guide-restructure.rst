..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================================
Architecture Design Guide Restructure
=====================================

Problem description
===================

Currently, the Architecture Design Guide is primarily organised by use case.
However, a combination of features from different use cases is often used when
designing an OpenStack cloud.

It is recommended to reorganise information so the user can consider all the
requirements, to help determine their OpenStack cloud architecture.
Additional information should be provided when designing an OpenStack cloud
in a development, staged or production environment. The proposal is to develop
a more detailed structure that creates an abstraction between cloud
architecture concepts and various OpenStack projects. This will make it
easier to maintain and update the guide.

Proposed change
===============

The proposed structure of the guide is to first describe common cloud use
cases, then general architectural concepts, followed by a Design chapter
with a detailed breakdown of the major cloud architecture components.

The section headings in the Design chapter would be as follows:

      #. Technical Detail
      #. Capacity and Scale
      #. High Availability
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

The headings are intended as a guideline to the type of information that should
be provided. It will be used only when there is a specific need to call out
the information.

Proposed Table of Contents
--------------------------

The new proposed structure for the Architecture Design Guide is as follows:

#. General Overview
#. Use Cases

   #. Development Cloud

      #. Stakeholder
      #. User Stories
      #. Design Model
      #. Component Block Diagram

   #. General Compute Cloud

      #. Stakeholders
      #. User Stories
      #. Design Model
      #. Component Block Diagram

   #. Web Scale Cloud

      #. Stakeholders
      #. User Stories
      #. Design Model
      #. Component Block Diagram

   #. Public Cloud

      #. Stakeholders
      #. User Stories
      #. Design Model
      #. Component Block Diagram

#. High Availability

   #. Overview

#. Capacity and Scale

   #. Overview

#. Design

   #. Compute

      *All topics related to the implementation of the compute platform,
      i.e. hypervisors, nova, ironic, etc.*

   #. Storage

      *All topics related to storage choices and the implementation of
      projects like cinder, manila, etc.*


   #. Networking

      *All topics related to networking design choices such as SDN, LBaaS
      and neutron.*


   #. Identity

      *Topics about authentication, authorisation and assignment at
      all levels for keystone and any other related projects.*


   #. Image

      *Topics about the management, creation, distribution and
      deployment of images for glance and other related projects.*


   #. Control Plane

      *Topics discussing the general implementation of the OpenStack
      control components and the decision making that goes into the
      choices that need to be made.*


   #. Dashboard and APIs

      *Topics about the interaction with cloud services using
      a graphical interface or the OpenStack APIs. This would
      include horizon and other Cloud Management Platform (CMP) tools.*


Alternatives
------------

Leave the guide as is

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  * shilla-saebi

Other contributors:
  * dazzachan
  * shaunom

Work Items
----------

  * Reach a consensus on the information architecture
  * Rework the abstract to clearly identify the audience and purpose
    of the book
  * Move content to improve information architecture
  * Identify information gaps and submit and fix bugs

Dependencies
============

None

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [arch-guide]
  in the subject, biweekly Ops Guide specialty team meeting,
  weekly documentation team meeting, and potentially etherpads.

.. _`Ops/arch tasks etherpad`: https://etherpad.openstack.org/p/ops-arch-tasks
