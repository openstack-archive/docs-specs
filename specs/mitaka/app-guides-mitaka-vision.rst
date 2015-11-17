..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=============================================
Application Developer Guides - aka API Guides
=============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/app-guides-mitaka-vision

We want to build comprehensive application developer documentation for
public-facing OpenStack REST APIs. These guides aim to empower
consumers to successfully build cloud-native applications. Each
comprehensive guide, delivered on developer.openstack.org, will contain a
collection of conceptual articles, reference information, and how-to
articles.

Problem description
===================

For years, we have published API references. However, application developers
also need conceptual, how-to, and best practice information.

Goals
=====

To better serve this developer.openstack.org audience, we plan to:

- Update the landing and web pages to make developer.openstack.org more usable
- Give application developers information based on their language of choice
- Source information about service capabilities and REST APIs through each
  service repository itself
- Ensure that the "First App on OpenStack" is a complete and
  easy-to-use first guide
- Automate the generation of API reference information
- Create excellent, helpful, accurate, sufficient app developer guides
- Standardize with the API Working Group doc guidelines in mind
- Organize the guides around developer tasks and workflow rather than around
  services

Proposed change
===============

With these general guidelines in mind, let's build a new guide from multiple
sources with this outline:

* Introduction to OpenStack REST APIs
* Build your First App on OpenStack
* Discover OpenStack services, workflows, and resources

  * Authenticate as a user
  * Inspect the service catalog
  * Decide what services and resources you need

    * Images

      * Manage images

    * Compute instances (VMs)

      * Understand flavors and images
      * Launch an instance
      * Provide user data to an instance
      * Manage access and security

        * Use keypairs
        * Use security groups

      * Migrate instances

    * Networks

      * Create networks, ports, routers, subnets
      * Load balance across servers

    * Block Storage

      * Attach volumes with block storage
      * Transfer a volume from server-to-server

    * Object Storage

* Troubleshoot apps on OpenStack
* Libraries and Software Development Kits

  * Python
  * Go
  * .Net
  * Java
  * nodejs
  * Ruby
  * PHP

* API Complete References
  Based on Swagger, each method should have the following information:

  * Method (GET/PUT/POST/PATCH/HEAD/DELETE)
  * Resource (identified by the URL)
  * Request parameters, type and description including whether it is optional
  * Request headers including media-type, content-type, accept, and others
  * Response headers (for some APIs)
  * Responses including types and description
  * Example request headers and body
  * Example response headers and body
  * Status codes: success and error response codes
  * Resource model: data types that can be consumed and produced

  These services are scoped for this team's work this release:

  * Identity
  * Compute
  * Images
  * Networks
  * Block Storage
  * Object Storage

* Best practices for apps on OpenStack

How will each section be sourced?

  * API Quick Start in the api-site repository
  * First App on OpenStack in the api-site repository
  * Refresh the landing page in the api-site repository
  * api-guide folder in each OpenStack service repository, such as nova
  * api-ref info containing migrated Swagger/RST source files

How will consumers find and read these articles? From:

 * http://developer.openstack.org
 * http://developer.openstack.org/firstapp-libcloud/
 * http://developer.openstack.org/api-guide/quick-start/
 * http://developer.openstack.org/api-guide/compute/
 * http://developer.openstack.org/sdks/ (needs a landing page, currently we use
   developer.openstack.org/#sdks, an anchor on the landing page)
 * http://developer.openstack.org/sdks/python/openstacksdk/

and so on as we fill out the outline above with content.

What about projects not in this outline?

This outline suggests a pattern for subsequent projects to follow. This
outline creates a framework for application developer docs. We expect trove,
sahara, ironic, and other projects to follow this pattern to best serve their
consumers.

Alternative
-----------

We could continue to produce specifications on specs.openstack.org combined
with API reference information and links to SDKs.

However as the OpenStack ecosystem expands, we want to foster the best
practices for application developers by providing the best experience through
the http://developer.openstack.org.

Implementation
==============

With the completion of both the WADL to Swagger/RST migration
proof-of-concept and the nova repository to developer.openstack.org site
publication proof-of-concept, the following Work items section
describes the remaining implementation tasks.

Assignees
---------

Primary assignee:
  russellsim Russell Sim

Other contributors:

 * annegentle Anne Gentle
 * etowes Everett Toews
 * sdague Sean Dague
 * kbhawkey Karen Hawkey
 * fifieldt Tom Fifield

Work items
----------

* Landing and web pages

  * Revise landing page for developer.openstack.org - russellsim
  * Create landing page for developer.openstack.org/sdks
    - russellsim
  * Create web pages for
    developer.openstack.org/sdks/python/openstacksdk - etoews

* Content

  * Complete First App on OpenStack matrix of SDK support (complete).
    Tom should keep communicating about it as he is. - fifieldt
  * Ensure that APIs that support micro-versions display that
    information - russellsim
  * Document the API guides system for teams, including how to write,
    where to write, what to write, to use the framework as it is intended -
    annegentle
  * Remove obsolete content from the SDK landing page. Both the .NET and PHP
    projects on the current landing page have been removed due to inactivity,
    see https://wiki.openstack.org/wiki/Stackforge_Namespace_Retirement#Inactive_Projects_to_Retire
    - annegentle
  * Create a new core review team for API documentation specifically including
    members of the API working group - annegentle

* Publication jobs

  * Write publishing jobs to statically copy Swagger/RST reference
    documentation from fairy-slipper to developer.openstack.org
    - russellsim, annegentle, and kbhawkey
  * Publish the Python SDK OpenStackSDK docs to
    developer.openstack.org - etowes

* Communication

  * Communicate the January 16th WADL freeze date for cut over to
    Swagger/RST - annegentle
  * Communicate what teams must do to follow this pattern -
    annegentle
  * Write a specification for the infrastructure project so that they
    understand our need for a server rather than static content for
    developer.openstack.org - russellsim

.. note:
   * Note, a UX dev from Internap is interested in working on landing pages
     after the first pass is complete.

Dependencies
============

* Proof-of-concept complete for fairy-slipper
* Move fairy-slipper into OpenStack Gerrit:
  https://review.openstack.org/#/c/245352/

Testing
=======

These deliverables use the tested openstackdocstheme Sphinx theme. No
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
