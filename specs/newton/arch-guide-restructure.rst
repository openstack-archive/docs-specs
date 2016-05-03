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
requirements first, to help determine their OpenStack cloud architecture.
Additional information should be provided when designing an OpenStack cloud
in a development, staged or production environment. The proposal is to develop
a more detailed structure that creates an abstraction between cloud
architecture concepts and various OpenStack projects. This will make it
easier to maintain and update the guide.

Proposed change
===============

Notes on content
----------------

The intention for the general structure of the guide is to begin by identifying
the common cloud use cases, and then lead into general architectural concepts
followed by a detailed breakdown of the major components in the design section.

The use of subsections in the Design Section are at the discretion of the
author, the intention is to create a structure that is used only when there
is a specific need to call out the information.

The suggested subsection headings for the section would be as follows. These
are also intended as a guidline to the type of information that should be
provided.

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations


TOC Structure
-------------

The following is the new proposed structure for the Arch Guide.


#. General Overview
#. Use Cases

   #. Development Cloud

      #. Stakeholder
      #. User Stories
      #. Design Model
      #. Component Block Diagram

   #. General Compute

      #. Stakeholders
      #. User Stories
      #. Design Model
      #. Component Block Diagram

   #. Web Scale

      #. Stakeholders
      #. User Stories
      #. Design Model
      #. Component Block Diagram

   #. Public Cloud

      #. Stakeholders
      #. User Stories
      #. Design Model
      #. Component Block Diagram

#. HA Concepts

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

      *Topics concerning authentication, authorisation and assignment at
      all levels covering Keystone and any other related projects.*


   #. Image

      *Topics that discuss the management, creation, distribution and
      deployment of images covering glance and other related projects.*


   #. Control Plane

      *Topics discussing the general implementation of the OpenStack
      control components and the decision making that goes into the
      choices that need to be made.*


   #. Dashboard & API's

      *Topics that cover the interaction with cloud services via both
      a graphical interface as well as through the API's. This would
      include Horizon and other CMP tools.*


Alternatives
------------

leave the guide as is

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
  in the subject, weekly Ops Guide specialty team meeting,
  weekly documentation team meeting, and potentially etherpads.

.. _`Ops/arch tasks etherpad`: https://etherpad.openstack.org/p/ops-arch-tasks
