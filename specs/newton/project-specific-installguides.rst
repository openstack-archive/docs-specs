..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===============================
Project specific Install Guides
===============================


Problem description
===================

With the growing OpenStack Big Tent, many projects need to create
Install Guides. The current Install Guide is concentrating on a small
set of projects and gets tested each release. Documenting and testing
all projects in the Install Guide is not possible with the current
size of the OpenStack Documentation team.

We therefore need to find a way that allows projects to write their
own Install Guides without involvement of  the Documentation team -
and the Documentation team acting as enabler for these documents.

Proposed change
===============

The basic Installation Guide will serve as a reference to reach the
first step where administrators have all the underlying services like
MySQL and RabbitMQ and a base set of functionality installed and
working. It is essential for every reader of the guide to have a
high-quality, proactively-checked, easy to understand content.

Then additional project specific guides can be written that pick up
from that base first step, assuming their readers have completed that
first step successfully.

Ownership of the project specific install guides is with the
respective project team, not the Documentation team. This means the
content is in a project specific repository, reviews will be done by
the project team, and bug reports will go in the bug queue of the
project.

The Documentation team will enable the project team to write the
project specific guides with mentoring, setting up needed
infrastructure, writing of guidelines, providing a working base
Installation Guide that the project specific guides can use as
reference.


Scope of basic Install Guide
----------------------------

The content of the basic Install Guide will cover the core projects
that every cloud needs, so this includes the projects defined as the
`starter-kit:compute
<http://governance.openstack.org/reference/tags/starter-kit_compute.html>`__
plus a few others:

* Compute service (nova): Part of starter-kit:compute.
* Image service (glance): Part of starter-kit:compute.
* Identity service (keystone): Part of starter-kit:compute.
* Networking service (neutron): Part of starter-kit:compute.
* Block storage service (cinder): Part of current Install Guide and
  required by many use cases.
* Dashboard (horizon): Part of current Install Guide and required by
  many users.

No further projects will be added to the guide unless they are
required by one of the existing projects or generally required to run
an OpenStack based cloud.

The Documentation team will update and test the Install Guide for each
release.

The Install Guide will be enhanced to link to additional project
specific install guides. For this, it will have in a separate chapter
for each official project a small section where each official project
can give a short summary of their project together with a link to
their own Install Guide.


For example, Orchestration could store their install guide in the ``heat``
repository, and publish to
http://docs.openstack.org/project-install-guide/mitaka/orchestration/ .

Then the chapter "Additional projects" would contain a small section:

.. code::

   Orchestration service (heat)
   ============================

   The Orchestration service enables you to X and Y. Installation is
   documented at
   http://docs.openstack.org/project-install-guide/mitaka/orchestration .


Docs.openstack.org index
------------------------

The project specific install guides will be listed not only in the
Install Guide but also be found from the docs.openstack.org web page.
An exact location will need to be found based on the number of guides.

Content of project specific install guides
------------------------------------------

The content of these project specific install guides is outside of the
control of the documentation team. For consistency with the base
Install Guide architecture and as part of the "enabling others" part,
the documentation team has some suggestions:

* We encourage projects to build on top of the existing Install Guide
  architecture. This way the project team guide does not need to
  document a full OpenStack setup including the basic host setup.
  Instead of reinventing the wheel, the project team guide can just
  point out differences for the specific project.

* We encourage projects to follow the documentation conventions as
  written down in the `Documentation Contributor's Guide
  <http://docs.openstack.org/contributor-guide/>`__.

* We encourage projects to use the same theme (called
  openstackdocstheme) as the Install Guide.

* We encourage projects to support the same distributions as the
  Install Guide does. They can either document installation of
  OpenStack packages from distributors or installation from source.

* Project specific guides should be versioned, so create a specific
  version for each release that gets published from their release
  branch.

* RST is the preferred documentation format and our tools for
  publishing work best with it. Also, translation of RST guides is
  easy to set up and working in the OpenStack CI infrastructure.
  Therefore, project teams should use RST as format.

* The project team installation guides should have a common naming
  scheme: "X Service Installation Guide" where X is the service name
  from the governance repository. So, for example "Orchestration
  Service Installation Guide".

Publishing
----------

Project teams can publish their content to
``docs.openstack.org/project-install-guide/RELEASE/SERVICE/ ``. ``RELEASE`` is
the release like ``mitaka`` or ``newton``, ``SERVICE`` is the service
name like ``orchestration``. For publishing from master, the
``RELEASE`` should be ``draft``.

This structure takes care that we do not share directories for
different projects.

Alternatives
------------

* No central Install Guide written by documentation team: Each
  distribution is asked to publish their own installation guide on a
  web domain they own, sourced from their own repositories. Each
  project team can write an "installation from source" installation
  guide that includes all the basic project infrastructure set up.
* Change scope of Install Guide, add a few more or less projects as
  proposed in this spec to it.
* Status quo: One central Installation Guide that is maintained by the
  documentation team and no project specific guides for those projects
  that are not part of the central guide.


Implementation
==============

Assignee(s)
-----------


Work Items
----------

* Move not anymore documented projects out of the guide in their own
  repositories: Orchestration (heat), Telemetry (telemetry), Object
  Storage (swift), Shared File system (manila).

* Create new chapter "project specific install guides" as skeleton.

* Create new project specific install guides section on
  http://docs.openstack.org .

* Create example jobs for publishing of project specific install
  guides (jaegerandi).

* Work with operator tags team to amend the `ops:docs:install-guide tag
  <http://git.openstack.org/cgit/openstack/ops-tags-team/tree/descriptions/ops-docs-install-guide.rst>`_
  (thingee)

Dependencies
============


Testing
=======


References
==========
