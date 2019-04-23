..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===============================
Project-specific install guides
===============================


Problem description
===================

With the growing OpenStack Big Tent, many projects need to create
install guides. The current install guide is concentrating on a small
set of projects and gets tested each release. Documenting and testing
all projects in the install guide is not possible with the current
size of the OpenStack documentation team.

We therefore need to find a way that allows projects to write their
own install guides without involvement of the documentation team -
and the documentation team acting as enabler for these documents.

Proposed change
===============

The basic install guide serves as a reference to reach the
first step where administrators have all the underlying services like
MySQL and RabbitMQ and a base set of functionality installed and
working. It is essential for every reader of the guide to have
high-quality, proactively-checked, easy-to-understand content. The intent for
a central, basic install guide is to train and orient readers so they can
understand multiple OpenStack services while making informed decisions for
their situation.

Then additional project-specific guides can be written that pick up
from that base first step, assuming their readers have completed that
first step successfully.

Ownership of the project specific install guides is with the
respective project team, not the documentation team. This means the
content is in an existing or new repository owned by the project team,
reviews will be done by the project team, and bug reports will go in
the bug queue of the project.

The documentation team enables the project team to write the
project specific guides with mentoring, setting up needed
infrastructure, writing guidelines, provision of a template ("cookie
cutter"), and providing a working base install guide that the project
specific guides can use as reference.


Scope of basic install guide
----------------------------

The content of the basic install guide will cover the infrastructure and
centralized projects that every cloud needs. This includes the projects defined
as the
`starter-kit:compute
<http://governance.openstack.org/reference/tags/starter-kit_compute.html>`__
plus a few others:

* Compute service (nova): Part of starter-kit:compute.
* Image service (glance): Part of starter-kit:compute.
* Identity service (keystone): Part of starter-kit:compute.
* Networking service (neutron): Part of starter-kit:compute.
* Block storage service (cinder): Part of current install guide and
  expected by most users.
* Dashboard (horizon): Part of current install guide and expected by
  most users.

No further projects will be added to the guide unless they are
required by one of the existing projects or generally required to run
an OpenStack based cloud.

The documentation team updates and tests the basic install guide for
each release.

The install guide will be enhanced to link to additional project
specific install guides. For this, it will have in a separate chapter
for each official project a small section where each official project
can give a short summary of their project together with a link to
their own install guide. The chapter will also explain that all these
projects are first-class citizens of the big tent of OpenStack.

For example, Orchestration could store their install guide in the ``heat``
repository, and publish to
http://docs.openstack.org/project-install-guide/mitaka/orchestration/ .

Then the chapter "Additional projects" would contain a small section
to introduce the service and link to it:

.. code::

   Orchestration service (heat)
   ============================

   The Orchestration service ...

   Installation is documented at
   http://docs.openstack.org/project-install-guide/mitaka/orchestration
   .


Docs.openstack.org index
------------------------

The project specific install guides will be listed not only in the
install guide but also be found from the docs.openstack.org web page.
An exact location will need to be found based on the number of guides.

Content of project specific install guides
------------------------------------------

The content of these project specific install guides is outside of the
control of the documentation team. For consistency with the base
install guide architecture and as part of the "enabling others" part,
the documentation team has some suggestions:

* We encourage projects to build on top of the existing install guide
  architecture. This way the project team guide does not need to
  document a full OpenStack setup including the basic host setup.
  Instead of reinventing the wheel, the project team guide can just
  point out differences for the specific project.

* We encourage projects to follow the documentation conventions as
  written down in the `Documentation Contributor Guide
  <http://docs.openstack.org/contributor-guide/>`__.

* We encourage projects to use the same theme (called
  ``openstackdocstheme``) as the install guide.

* We encourage projects to support the same distributions as the
  install guide does. They can either document installation of
  OpenStack packages from distributors or installation from source.

* Project specific guides should be versioned, so project teams should
  publish to the respective subdirectory for their service.

* RST is the preferred documentation format and our tools for
  publishing work best with it. Also, translation of RST guides is
  easy to set up and working in the OpenStack CI infrastructure.
  Therefore, project teams should use RST as format.

* The project team installation guides should have a common naming
  scheme: "X Service install guide" where X is the service name
  from the governance repository. So, for example "Orchestration
  Service install guide".

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

* Packaged install guides separated out, with no single-sourced install guide:
  each distribution publishes their own installation guide. These guides can
  be published to docs.openstack.org/install or to a web domain they own,
  sourced and reviewed from their own repositories with their teams. These
  teams can set their own publishing schedule. This alternative solution
  does not address the project teams needs, but alleviates the resource drain
  on a centralized docs team.
* Stop writing package-based install guides in the OpenStack git namespace
  entirely. Instead, have a central team write a starter-kit-based guide that
  describes the multiple available deployment options and publish to
  docs.openstack.org. This solution may be already available when readers
  browse the distro marketplace at
  https://www.openstack.org/marketplace/distros/.
* Each project team can write an "installation from source" installation
  guide that includes all the basic project infrastructure set up.
* Change scope of install guide, add a few more or less projects as
  proposed in this spec to it. This does not address the current single-
  sourcing with packages problem described, however.
* Status quo: One central install guide that is maintained by the
  documentation team and no project specific guides for those projects
  that are not part of the central guide. This approach does not scale
  unless we receive a commitment of resources from each project in the
  installation guide.
* One central guide that is reviewed by the documentation team - like
  today - and only projects are documented when the project team has
  committed writing, testing, and updating the chapter.

  This does not scale since reviewing would still be done by the
  documentation team. Experience in the past has shown that project
  teams need to be reminded of their commitment, so in the end the
  documentation team would play a large coordination and shepherding
  role for such a large guide - instead of following the enablement
  role that is sought by this proposal.

Implementation
==============

Assignee(s)
-----------

* Lana Brindley (loquacities) - Docs PTL
* Install Guide Speciality Team

Work Items
----------

* Move projects that are now out of scope of the basic install guide
  into in their own repositories. Also, create initial skeleton for
  these project specific install guides so that project teams have a
  consistent starting point that others can follow as example.

  This affects: Orchestration (heat), Telemetry (telemetry), Object
  Storage (swift), Shared File system (manila).

* Create new chapter "project specific install guides" as skeleton.

* Create new project-specific install guides section on
  http://docs.openstack.org .

* Create example jobs for publishing of project-specific install
  guides (jaegerandi).

* Work with operator tags team to amend the `ops:docs:install-guide tag
  <http://opendev.org/openstack/ops-tags-team/tree/descriptions/ops-docs-install-guide.rst>`_
  (thingee)

* Create a "cookie cutter" template for use by projects when creating
  new Install Guides.

Dependencies
============


Testing
=======


References
==========

* http://lists.openstack.org/pipermail/openstack-dev/2016-March/090214.html
* https://www.openstack.org/assets/survey/April-2016-User-Survey-Report.pdf
* https://review.openstack.org/#/c/310588/
