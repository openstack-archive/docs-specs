..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=========================
Newton Installation Guide
=========================


Problem description
===================

With the growing OpenStack Big Tent, many projects need to create
install guides, new infrastructure is planned to enable projects to write
and maintain their own install guides, and to have them published on
docs.openstack.org as first class OpenStack citizens. As a complement to
this, the current install guide needs to be updated and improved to ensure
it remains a good source of installation information, with an increased
focus on the fact that the install guide is used as training material, and
is not recommended as a way to install clouds for production.

This spec proposes some changes to the install guide to meet this end, and
is the product of discussion at the Newton design summit (see references).

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

* Update the title (what to?) to reflect that it is for training and not
production, and add preamble to explain that purpose.
* Document from packages to best use existing content, but continue to
revisit this problem over time, as more data emerges about which
installation method users prefer.
* Edit the existing content so that it uses manual configuration only.
* Create a new mailing list for Install Guide matters.

Dependencies
============


Testing
=======


References
==========

* https://etherpad.openstack.org/p/austin-docs-workgroup-install
