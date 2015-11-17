..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=============================================
Application Developer Guides - aka API Guides
=============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/app-guides-mitaka-vision

We want to build comprehensive app developer documentation for public-facing
REST APIs for OpenStack. This goal can be achieved by creating developer guides
for consumers to successfully build cloud-native applications. These developer
guides have conceptual articles, reference information, and how-to
articles collected into one comprehensive guide on developer.openstack.org.

Problem description
===================

For years now we have published API documentation, but application developers
need much more information than simply API documentation. With the API
reference information as an article in the collection of information, we can
better serve this audience through developer.openstack.org by:

- updating the landing page for developer.openstack.org
- giving application developers information based on their language of choice
- sourcing information about service capabilities and REST APIs through each
service repo itself
- ensuring that the "First App on OpenStack" is a complete first guide
- automating the generation of API reference information
- creating excellent, helpful, accurate, sufficient app developer guides
- standardizing with the API Working Group doc guidelines in mind
- aiming for organization of app developers tasks and workflow, rather than a
"service-first" optimization

Proposed change
===============

With these general guidelines in mind, let's build a new guide from multiple
sources with this outline:

* Introduction to OpenStack REST APIs
* Building your First App on OpenStack
* Identity API

  * Authenticate as a user

* Images

  * Manage images

* Compute

  * Launch an instance
  * Provide user data to an instance
  * Manage access and security

    * Using keypairs
    * Using security groups

  * Migrating instances

* Networks

  * Create networks, ports, routers, subnets
  * Load balancing across servers

* Block Storage

  * Attach volumes with block storage
  * Transfer a volume from server-to-server

* Object Storage
* Troubleshooting Apps on OpenStack
* Libraries and Software Development Kits

  * Python
  * Go
  * .Net
  * Java
  * nodejs

* API Complete References
  Based on Swagger, each method should have the following information:

  * Method (GET/PUT/POST/PATCH/HEAD/DELETE)
  * Resource (Identified by the URL)
  * Request parameters, type and description including whether it is optional
  * Request headers including media-type, content-type, accept, and others
  * Response headers (for some APIs)
  * Responses including types and description
  * Example request body and headers
  * Example response body and headers
  * Status codes: successful request and error responses
  * Resource model: describes data types that can be consumed and produced

  These are the services scoped for this team's work this release:
  * Identity
  * Compute
  * Images
  * Networks
  * Block Storage
  * Object Storage

* Best Practices for Apps on OpenStack

How will each section be sourced?
    * API Quick Start in the api-site repo
    * First App on OpenStack in the api-site repo
    * refresh the landing page in the api-site repo
    * api-guide folder in each OpenStack service repository, such as nova
    * api-ref info containing migrated Swagger/RST source files

How will consumers find and read these articles? From:

 * http://developer.openstack.org
 * http://developer.openstack.org/firstapp-libcloud/
 * http://developer.openstack.org/api-guide/quick-start/
 * http://developer.openstack.org/api-guide/compute/
 * http://developer.openstack.org/sdk/ (needs a landing page, currently we use
   developer.openstack.org/#sdk, an anchor on the landing page)
 * http://developer.openstack.org/sdk/python/openstacksdk/

and so on as we fill out the outline above with content.

What about projects not in the outline above?
The outline above should give ideas for the rest of the projects to follow. The
intent is to build a framework to provide the best application developer docs.
We expect trove, sahara, ironic, and others to follow this pattern to best
serve their consumers.

Alternatives
------------

We could continue to produce only specifications on specs.openstack.org in
combination with API reference information and links to SDKs. However as the
ecosystem surrounding OpenStack expands we want to foster the best practices
for application developers by providing the best experience through the
existing http://developer.openstack.org.

Implementation
==============

With the proof-of-concept for migrating from WADL to Swagger/RST complete, and
a proof-of-concept for publishing from the nova repo to the
developer.openstack.org site complete, the remaining implementation tasks are
described in the Work Items below.

Assignee(s)
-----------

Primary assignee:
  russellsim Russell Sim

Other contributors:

 * annegentle Anne Gentle
 * etowes Everett Toews
 * sdague Sean Dague
 * kbhawkey Karen Hawkey
 * fifieldt Tom Fifield

Work Items
----------

 * Revise landing page for developer.openstack.org - russellsim *
 * Create landing page for developer.openstack.org/sdk - russellsim *
 * Create documentation pages for
   developer.openstack.org/sdk/python/openstacksdk - etowes
 * Write publishing jobs to statically copy Swagger/RST reference documentation
   from fairy-slipper to developer.openstack.org - russellsim and annegentle
   and kbhawkey
 * Communicate a WADL freeze date of January 16th for cutover to Swagger/RST -
   annegentle
 * Publish the Python SDK OpenStackSDK docs to developer.openstack.org - etowes
 * Complete First App on OpenStack matrix of SDK support (the matrix is done,
   Tom should keep communicating about it as he is) - fifieldt
 * Document what teams can do to follow this pattern - annegentle
 * Ensure microversions are displayed in the API reference information for the
   services that support microversions - russellsim
 * Write a specification for the infrastructure project to understand our need
   for a server rather than static content for developer.openstack.org -
   russellsim

.. note:
   * Note, a UX dev from Internap is interested in working on landing pages
     after the first pass is complete.

Dependencies
============

* Proof-of-concept completeness and defining complete for fairy-slipper

* Bringing fairy-slipper into OpenStack Gerrit:
  https://review.openstack.org/#/c/245352/

Testing
=======

These deliverables should use the tested openstackdocstheme Sphinx theme. No
additional testing resources are expected at this time.

References
==========

* http://specs.openstack.org/openstack/docs-specs/specs/liberty/api-site.html

* http://specs.openstack.org/openstack/api-wg/guidelines/api-docs.html

* https://etherpad.openstack.org/p/nova-v2.1-api-doc

* https://etherpad.openstack.org/p/Mitaka-Docs-API

* http://superuser.openstack.org/articles/openstack-application-developers-share-insights

* http://developer.openstack.org

* http://developer.openstack.org/firstapp-libcloud/

* http://developer.openstack.org/api-guide/quick-start/

* http://developer.openstack.org/api-guide/compute/
