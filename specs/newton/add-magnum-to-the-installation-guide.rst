..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Add magnum to the installation guide
====================================

https://blueprints.launchpad.net/openstack-manuals/+spec/add-magnum-to-the-installation-guide

Problem description
===================

Similar to the other services, magnum needs an installation guide for
operators. Currently, only development guides describe how to install magnum
from source or with Devstack. This guide will have the same structure with the
all other services' guides.

A project without an installation guide isn't appealing to operators, so an
installation guide will increase the acceptance of the project.

Finally, magnum packages are available in newton.

Other documents also already support magnum:
- `Magnum command-line reference <http://docs.openstack.org/cli-reference/magnum.html>`__

Proposed change
===============

Describe:
* database creation
* user, service and endpoint creation
* package installation for different distributions
* magnum configuration
* installation verification

Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  strigazi

Work Items
----------

None

Dependencies
============

Mitaka milestone or RC packages for each distribution supported by the
Installation Guide.

Testing
=======

Validate magnum deployment on all distributions supported by the installation
guide.

References
==========

Magnum-conductor and Magnum-api reside on the controller node similar to
glance-registry and glace-api, so the installation guide of glance was used as
reference.
