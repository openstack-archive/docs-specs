..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Architecture Design Guide Restructure
==========================================


Problem description
===================

Currently, the Architecture Design Guide is primarily organised by use case.
However,a combination of features from different use cases is often used when
designing an OpenStack cloud.

It is recommended to reorganise information so the user can consider all the
requirements first, to help determine their OpenStack cloud architecture.
Additional information should be provided when designing an OpenStack cloud
in a development, staged or production environment. The initial proposal is
to reorganise cloud design requirements into chapters, and consolidate use
case examples into a single chapter.



Proposed change
===============

The following is the new proposed structure for the Arch Guide.

#. General Overview
#. Use Cases

   #. Private Cloud

      #. Development
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

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

   #. Storage

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

   #. Networking

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

   #. Identity

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

   #. Image

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

   #. Control Plane

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations

   #. Dashboard

      #. Technical Detail
      #. Capacity & Scale
      #. HA
      #. Operator Requirements
      #. Deployment Considerations
      #. Maintenance Considerations




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

* conversion of ops guide architecture section to RST.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [arch-guide]
  in the subject, weekly Ops Guide specialty team meeting,
  weekly documentation team meeting, and potentially etherpads.

.. _`Structure Etherpad`: https://etherpad.openstack.org/p/ops-arch-tasks
