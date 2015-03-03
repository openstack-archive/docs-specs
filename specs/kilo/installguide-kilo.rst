..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================================
Installation Guide - Changes for Kilo
=====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/installguide-kilo

Implement mandatory changes and optional enhancements to the Installation
Guide for Kilo.

Problem description
===================

The installation guide requires certain changes to make it work for each
release of OpenStack.

Proposed change
===============

* Implement mandatory changes and potentially one or more optional
  enhancements.

Alternatives
------------

None.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Matt Kassawara (ionosphere80)

Other contributors:
  Anyone with installation experience

Work Items
----------

* Mandatory changes

  * Overall

    - As necessary, make changes to successfully install OpenStack on
      Ubuntu 14.04, RHEL 7, CentOS 7, Fedora 21, SLES 12, and openSUSE
      13.2 using native methods.

    - For RabbitMQ, create and use "openstack" account instead of the
      guest account.

    - As necessary, note that stock configuration files might require
      adding configuration stanzas/options rather than editing them.

    - As necessary, change any defaults in stock configuration files
      that generate deprecation warnings.

  * Block Storage

    - Replace deprecated v1 API with v2 API.

* Optional changes

  * Overall

    - Install upstream RabbitMQ package because distributions often include
      old versions.

    - Replace deprecated (?) python-serviceclient commands with generic
      python-openstackclient commands.

    - Enable Identity v3 API.

    - Install optional services using source if a distribution lacks
      packages.

  * Compute

    - Enable v3 API.

  * Networking

    - Standardize location for Open vSwitch agent configuration.

    - Add content for Linux Bridge agent.

Dependencies
============

* Kilo milestone or RC packages for each distribution supported by the
  installation guide.

Testing
=======

* All distributions supported by the installation guide must complete
  `testing`_ of at least core services (Identity, Image Service, Compute,
  and Networking) and successfully launch an instance using both legacy
  networking (nova-network) and Networking (neutron). Distributions that
  do not meet these criteria risk temporary removal from publication.

.. _`testing`: https://wiki.openstack.org/wiki/KiloDocTesting

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [install-guide]
  in the subject, weekly documentation team `meeting`_, and potentially
  etherpads.

.. _`meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting
