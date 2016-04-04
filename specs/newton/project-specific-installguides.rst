..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===============================
Project Specific Install Guides
===============================

Problem description
===================

With the growing OpenStack Big Tent, many projects like to create
Install Guides. The current Install Guide is concentrating on a small
set of projects and gets tested each release. Documenting and testing
all projects in the Install Guide is not possible with the current
size of the OpenStack Documentation team.

We therefore need to find a way that allows projects to write their
own Install Guides without involvement of  the Documentation team -
and the Documentation team acting as enabler for these documents.


Proposed change
===============


Install Guide will cover the core infrastructure projects only:
Compute service, Identity service, Networking service, Image service,
Block Storage service, and Object Storage service.

The documentation team will update and test the guide for each
release.

No further projects will be added to the guide unless they are
required by one of the existing projects or generally required to run
an OpenStack based cloud.

Since OpenStack has grown and contains many more projects, the
documentation team will concentrate on the core projects in the
Install Guide and give other projects a place and a frame work to
create their own Install Guides that they can maintain completely
outside of the Documentation team repositories.

The Install Guide will be enhanced to link to additional "project
specific Install Guides". For this, it will have in a separate chapter
for each official project a small section where each official project
can give a short summary of their project together with a link to
their own Install Guide.

For example, Orchestration could store their install guide in the heat
repository, and publish to 
http://docs.openstack.org/developer/heat/install-orchestration


The project specific Install Guides will thus be listed on the
docs.openstack.org web page and also in the Install Guide.

The content of these project specific Install Guides is out side of
the control of the documentation team. For consistency with the base
Install Guide architecture:

* We encourage projects to build on top of the existing Install Guide
  architecture. This way they do not need to document a full OpenStack
  setup but can just point out differences for their project.

* We encourage projects to follow the documentation conventions as
  written down in the Contributor's Guide.

* We encourage projects to use the same theme (called
  openstackdocstheme) as the Install Guide.

* We encourage projects to support the same distributions as the
  Install Guide does.


Alternatives
------------

* Keep some more projects in the guide.
* Have each distro publish an installation guide on a web domain they
  own, sourced from their own repositories. Then each project could
  write an "install from source" installation guide that includes all
  the basic project infrastructure set up.
* None that scales.



Implementation
==============

* Move not anymore documented projects out of the guide:
  Orchestration, Telemetry, Shared File system.
* Create new chapter "project specific Install Guides" linking to other guides
* Create new project specific Install Guides section on
  http://docs.openstack.org

Assignee(s)
-----------


Work Items
----------


Dependencies
============


Testing
=======


References
==========
