..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================================
Writing your First OpenStack Application
========================================


Problem description
===================

Currently, OpenStack is missing documentation similar to other Python
projects, that introduces a new user to the API. One well known "first
app" tutorial in the Python community is the Django web framework's
`tutorial <https://docs.djangoproject.com/en/dev/intro/tutorial01/>`_.

Proposed change
===============

A guide has been written by members of the Application Ecosystem WG
that introduces the OpenStack API, using a non-trivial Python application
that serves as a teaching tool - similar to the poll app in the
equivalent Django tutorial.

Alternatives
------------

None

Implementation
==============

This book has been written for software developers who wish to deploy
applications to OpenStack clouds.

We’ve assumed that the audience is an experienced programmer, but that
they  haven’t necessarily created an application for cloud in general, or
for OpenStack in particular.

In addition to learning to deploy applications on OpenStack, the reader
will also learn some best practices for cloud application development.

This tutorial actually involves two applications; the first, a fractal
generator, simply uses mathematical equations to generate images.
However, really, it’s just an excuse; the real application is the code that
enables the reader to make use of OpenStack to run it. That application
(and therefore this guide) includes:

*    Creating and destroying compute resources.
*    Cloud-related architecture decisions, such as microservices and modularity
*    Scaling up and down to customize the amount of available resources.
*    Object and block storage for persistance of files and databases.
*    Orchestration services to automatically adjust to the environment.
*    Networking customization for better performance and segregation.
*    A few other crazy things we think ordinary folks won’t want to do ;).


The guide has been written with a strong preference for the most common
API calls, so it will work across a broad spectrum of OpenStack versions.
In addition, the authors have paid special attention that the first 3 sections
should work almost regardless of OpenStack cloud configuration (basically
Nova, Keystone and Glance are the only requirements, but neutron will be used
if installed).


Repository Location
-------------------

This content should be published to developer.openstack.org

The content created during the sprint should be separated from the app.

The content created during the sprint documents how to use the OpenStack API
and several OpenStack SDKs and the app is only an example use case. In theory
the used app (Faafo at the moment) can be replaced in the future (or maybe we
want to add a second use case) by an other app.
Additionally, the focus of the documentation placed inside the repository of
the app is different from the focus of the content created during the sprint.
The documentation inside the repository of the app describes how to use
the app itself (how to create a development environment, example outputs, ..),
not how to use OpenStack SDKs and the OpenStack API.


Multi-SDK support
-----------------

The guide has been written so that support for multiple SDKs is a core part of
its publication. Initial sections have been written for libcloud, and section1
is also available for fog. The design philosophy is that the same prose can be
used, with code samples swapped.


Assignee(s)
-----------

* Sean M. Collins (sean@coreitpro.com)
* Tom Fifield (tom@openstack.org)
* James Dempsey (jamesd@catalyst.net.nz)
* Nick Chase (nchase@mirantis.com)
* Christian Berendt (christian@berendt.io)

Work Items
----------

* Write content during the sprint


Dependencies
============

None


Testing
=======

The guide is written in such a way that all examples can
be run by the reader, and steps have been taken to verify that
all content is valid.


References
==========

* `[Openstack-operators] Fostering OpenStack Users <http://lists.openstack.org/pipermail/openstack-operators/2014-December/005788.html>`_

* `Application Eco WG - meeting - "first app tutorial" <https://www.youtube.com/watch?v=ahc5IsUdeK0>`_
