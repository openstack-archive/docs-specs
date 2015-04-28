..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
High Availability Guide Improvements
====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/improve-ha-guide

This guide provides Openstack cloud operators with configuration
details and best practices guidelines for creating a highly-available
cloud environment. This is critically important if OpenStack is to
"win the enterprise". This restructure will offer readers a more
logical flow between an initial installation and adopting high
availability components for an OpenStack cloud. Additionally, it
should reduce the content maintenance burden of the Docs team in
general by reducing duplication. We’ve prepared a draft table of
contents for the `HA Guide restructure
<https://wiki.openstack.org/wiki/HAGuideImprovements/TOC>`__

along with starting notes for included content.

Problem description
===================

This will be an HA Installation Guide; information about how to manage an
existing HA environment (such as how to recover from a failed component) is
beyond the scope of this project.

The strategic assumptions are:

#. We assume that users have already built at least a "learning" OpenStack
environment following the information in the Install Guide before they
attempt to set up an HA environment. The HA Guide should be targeted at
users who have some experience installing OpenStack.

#. The HA Guide should be structured to parallel the Install Guide as much
as possible. This means that the installation information will be
structured sequentially, around the OpenStack components rather than HA
strategies (active/passive vs active/active). The high-level flow is:

    - HA Intro and Concepts
    - Hardware setup
    - Infrastructure prerequisites that we assume are in place before starting
      an HA deployment or upgrade
    - HA networking -- Neutron only (very high-level with handoff to Networking
      Guide)
    - HA configuration for Controller services
    - HA configuration for Storage services, including brief discussion of the
      advantages of Ceph and a handoff to Ceph documentation for configuration
      details
    - HA configuration for Compute node services
    - Other HA configuration (Ceilometer/MongoDB, Heat, Trove)

#. The HA Guide should heavily reference the Install Guide and will then
supplement that information. For example, "Install and configure the xx
component following the instructions in the Install Guide, then do these
additional configurations." This will minimize content duplication.

#. Similarly, we expect that the Networking Guide will handle
high-availability networking configuration and the HA Guide will reference
that material.

#. The HA Guide should emphasize a reasonable, standard deployment based on
open source components. We can provide some notes about alternatives as
appropriate (for example, using a commercial load balancer might be a
better alternative than relying on HAProxy).

#. In general, the HA Guide should only cover core OpenStack services.
Other projects (such as Sahara and Murano) should cover HA configurations
in their documentation.

#. The HA guide should cover all appropriate Linux distros/platforms.

#. We will reuse as much of the material in the existing HA Guide as
possible, with revisions to augment and update the information. The revised
document will be written in RST; existing content will be converted as it
is added to the new document.

#. Some attempt will be made to incorporate material for both the Juno and
Kilo releases, identifying configurations, etc that are different for these
releases.

Proposed change
===============

The guide should remain in the ha-guide repository with the set of
reviewers currently assigned. The guide should be re-written with the
assumptions outlined in the Problem description above.

The source must be set up to use `intersphinx
<http://sphinx-doc.org/latest/ext/intersphinx.html>`__ to support
copious cross-references between the HA Guide and the Install Guide.

Alternatives
------------

- Maintain the current structure, splitting between active/active and
  active/passive. This puts the onus on the user to figure out what to
  do in what order.

- Fully incorporate HA configuration information into the Install
  Guides. This would really complicate the process of creating and
  maintaining the Install Guides and would defeat the goal of having
  the Install Guides be easy to follow for people who are new to
  OpenStack and may also be new to Linux.

- Create a comprehensive HA Install Guide that replicates relevant information
  from the Install Guides. This would create a maintenance nightmare.

- Relegate all HA configuration information
  to the documentation for the individual components.
  This would make it very difficult for the user to get the "big picture"
  about how to implement HA for an environment.
  While we plan to have the details of HA for networking
  and many non-core services covered in the documentation for those pieces,
  we need a single document that details the process
  of getting the major Controller services configured for HA
  and provides a roadmap for all HA configuration.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  mattgriffin

Other contributors:
  <launchpad-id or None>

Work Items
----------

Revise based on https://wiki.openstack.org/wiki/HAGuideImprovements/TOC.

Create build and automation for RST rather than DocBook especially considering
much of the content is new and the current Active/Active and Active/Passive
structure will be abandoned.

Structure in parallel with Install Guide.

Heavily rely on Networking Guide scenarios.


Dependencies
============

* May require tight linking with the Install Guide(s). Be sure to track
  carefully with any blueprint for improvements to the Install Guide(s).


Testing
=======

Testing a high-availability cluster does require a lot of hardware and probably
a lab.

References
==========

* http://lists.openstack.org/pipermail/openstack-docs/2015-March/006058.html

* http://lists.openstack.org/pipermail/openstack-docs/2015-March/006012.html

* http://lists.openstack.org/pipermail/openstack-docs/2015-April/006225.html

* https://wiki.openstack.org/wiki/HAGuideImprovements/TOC
