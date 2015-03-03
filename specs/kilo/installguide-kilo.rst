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

The installation guide requires certain changes to make it work for the
Kilo release of OpenStack.

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

    - As necessary, replace "tenant" with "project" to align with
      Identity v3 API terminology.

    - As necessary, replace "message broker" with "message queue" to
      improve wording.

  * Identity

    - Enable version 3 API.

    - Replace deprecated eventlet (default web server) with Apache using
      `configuration`_ in upstream keystone repository.

      .. _`configuration`: https://github.com/openstack/keystone/tree/master/httpd

    - Replace SQL token storage driver with Memcached to improve
      performance.

    - Replace deprecated python-keystoneclient commands with
      python-openstackclient commands.

  * Image Service

    - Enable version 2 API.

  * Block Storage

    - Replace deprecated v1 API with v2 API.

* Optional changes

  * Overall

    - Where available, use the /etc/mysql/conf.d directory for additional
      database configuration.

    - Install upstream RabbitMQ package because distributions often include
      old versions.

    - Replace python-serviceclient commands with generic
      python-openstackclient commands.

    - Install optional services using source if a distribution lacks
      packages. For example, designate and sahara.

  * Networking

    - Standardize location for Open vSwitch agent configuration.

    - Add content for Linux Bridge agent.

  * Object Storage

    - Add content for standalone (keystone + swift) deployment.

Note: To simplify patches and shrink the review cycle, patches can
address one distribution rather than all distributions. Use separate
patches to address the same content for additional distributions.
Reviewers should take this into account so that one distribution
can complete patches, tests, and publication independent of other
distributions.

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
  in the subject, weekly installation guide `specialty team meeting`_,
  weekly `documentation team meeting`_, and potentially etherpads.

.. _`specialty team meeting`: https://wiki.openstack.org/wiki/Documentation/InstallGuide

.. _`documentation team meeting`: https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting
