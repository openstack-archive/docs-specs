..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

================================
Rework API Reference Information
================================

The blueprint we'll use to track this work supersedes prior blueprints that are
listed in the References section.

https://blueprints.launchpad.net/openstack-manuals/+spec/api-site

The API Reference site needs an update and better methods for maintaining and
providing accurate information for application developers using different cloud
provider's cloud resources.

Problem description
===================

With this blueprint we want to solve the following problems:

* API reference information has been historically difficult to
  community-source or company-partner source due to the specialized nature of
  both the tools and the REST API knowledge.
* API reference information needs to be sourced where API writers, API
  developers, contributor developers, API working group can review together.

This blueprint should provide a major rework of the way we provide upstream API
reference information to cloud users. The intended audience targets application
developers and SDK developers who need precise and accurate information about
each service's REST APIs. This is not API information for internal APIs such as
the RPC API used by the Compute project (nova) for scheduling compute hosts,
for example. These references are used to build a correct API call with the
correct request parameters and double-check your cloud provider's results
against the results you see on screen when you make a call.

There are currently 915 GET/PUT/POST/DELETE/PATCH calls documented on the
OpenStack API Complete Reference site at
http://developer.openstack.org/api-ref.html.

Currently, the API reference is in a separate repo, api-site. In the kilo
release (Nov14-Apr15) we moved all "narrative" information to the repo of the
project's choosing. For most projects, that location was the <project>-spec
repo. For Compute and Object Storage, it was their project's doc/source repo.
The API reference information remained in api-site repo. Do we continue to
enable the project teams to indicate where they want to maintain API reference
information? With the growth of teams with REST APIs to more than 20, we need
to either prioritize which REST APIs get support of a central doc team for API
docs, or strictly enforce where API reference information is maintained and
built from.

Ideally we will enable teams to review while bringing all the sources together
into one consumable, readable guide to the various services's REST APIs. These
should be handy Developer Guides that provide a unified view of
separately-sourced information.


Scope for Liberty release
-------------------------

For the first set of developer guides sourced across multiple repos with
automation for reference information, the scope will be limited to
infrastructure services used most based on the most recent User Guide survey.

* Identity v2.0
* Compute v2
* Block Storage v2
* Image service v2

Already documented in api-site:

* ceilometer: Telemetry or Telemetry module
* cinder: OpenStack Block Storage (two versions)
* glance: OpenStack Image service (two versions)
* heat: Orchestration or Orchestration module
* keystone: OpenStack Identity (two versions)
* neutron: OpenStack Networking
* nova: OpenStack Compute (two versions)
* sahara: Data processing service for OpenStack
* swift: OpenStack Object Storage
* trove: Database service for OpenStack

API docs elsewhere or unknown state:

* barbican: Key management service
* ironic: Bare metal service
* tripleo: Deployment
* zaqar: Message service
* designate: DNS service
* magnum: Containers service
* murano: Application catalog
* congress: Non-domain specific policy enforcement
* rally: Benchmark service
* mistral: Workflow service

Proposed change
===============

Requirements include:

Authoring: Information and source must be maintained and reviewed by project
developers with API working group informed and doc team providing support.

Authoring: API reference information should be auto-generated with strings
stored in the code. Review the :ref:`overview-of-standards` below.

Authoring: API reference information review should use the APIImpact and
DocImpact flags.

Authoring: Need an open-source toolchain for authoring.

Output: Output must offer a great experience for SDK developers and
application developers consuming OpenStack cloud resources. Optionally, it
would offer a "try it out" sandbox for each call against TryStack when using
authenticated credentials.

Output: Output should indicate which version of OpenStack will support a
particular API version, and within extensible APIs like Compute and Identity,
indicate which version a particular extension is available with.

Output: Since we may need a phased approach for timing and scoping, should work
with current docs such as with redirects or integrated displays.

Build: Must be automated based on Gerrit review and workflow.

Scope: Must be viable within six month release period.

Optional features:

Build: Optionally, build pieces that any cloud provider could then consume and
re-use in their customer documentation.

Contract validation: Optionally, must provide validation of requests and
responses as valid and would work against a public cloud endpoint.

.. _overview-of-standards:

Overview of standards
---------------------

Swagger: community-maintained standard, open-source tooling. Allows for
inclusion of content similar to our current entities. To output the information
you must run a server that renders the content. Current community-maintained
specification for content is version 2, see https://github.com/swagger-api/swagger-spec/blob/master/versions/2.0.md.

RAML: community-maintained standard, proprietary tooling unless you just edit
in text, but then how do you validate? Allows for inclusion of content similar
to our current entities.

..todo:: List more pros and cons of each standard.

JSON schema would be required for our API requests validation, to see if the
contract is being upheld. For example, request parameters, many of which are
defined as "plain" parameters, and some of which have multiple array-based
needs in the request that would have to be defined with JSON schema.

Example: Here's a sample request for adding personality to a Create Server
POST /v2/{tenant_id}/servers::

   "personality": [
            {
               "path": "/etc/banner.txt",
               "contents": "ICAgICAgDQoiQSBjbG91ZCBkb2VzIG5vdCBrbm93IHdoeSBpdCBtb3ZlcyBpbiBqdXN0IHN1Y2ggYSBkaXJlY3Rpb24gYW5kIGF0IHN1Y2ggYSBzcGVlZC4uLkl0IGZlZWxzIGFuIGltcHVsc2lvbi4uLnRoaXMgaXMgdGhlIHBsYWNlIHRvIGdvIG5vdy4gQnV0IHRoZSBza3kga25vd3MgdGhlIHJlYXNvbnMgYW5kIHRoZSBwYXR0ZXJucyBiZWhpbmQgYWxsIGNsb3VkcywgYW5kIHlvdSB3aWxsIGtub3csIHRvbywgd2hlbiB5b3UgbGlmdCB5b3Vyc2VsZiBoaWdoIGVub3VnaCB0byBzZWUgYmV5b25kIGhvcml6b25zLiINCg0KLVJpY2hhcmQgQmFjaA=="
            }
         ]

So another idea would be to not use Swagger or RAML or another standard that
comes along and instead just write RST with JSON schema, what are the benefits
of this approach? We already have RST expertise, we do not have JSON schema
experts though.

Questions and considerations
============================

Should we do a proof of concept for say, Compute, then have the other projects
follow? Identity v3 has the most calls in the core with 74, but Compute v2 plus
extensions has over 120 calls. Perhaps a better approach is a proof of concept
with Images as it's a fairly small API with 15 calls.

Alternatives
------------

Could keep what we currently have in api-site and WADL. However this requires
the continued use of clouddocs-maven-plugin for builds, which currently has no
maintainers.

Another consideration would be to put this spec as a guideline document for
writing API docs, rather than implementing through the docs team.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  annegentle

Other contributors:
  cberendt

Work Items
----------

Proof of concept automating API reference information with Image service.

Proof of concept aggregating information across separate repos in their
respective doc/source directories.

Web design and development of templates for new developer guide.

Dependencies
============

* Include specific references to specs and/or blueprints in glance, or in other
  projects, that this one either depends on or is related to.

* If this requires functionality of another project that is not currently used
  by docs: document that fact.

* Does this feature require any new library dependencies or code otherwise not
  included in OpenStack? Or does it depend on a specific version of library?


Testing
=======

Output should be tested for cross-browser, cross-operating-system
compatibility.

Authoring environment should be tested for cross-operating-system
compatibility.

References
==========

Previous unimplemented blueprints related to this spec:

* https://blueprints.launchpad.net/openstack-manuals/+spec/autogenerate-api-reference
  I don't believe we want to autogenerate if we want these docs to serve
  as a contract for testing purposes.
* https://blueprints.launchpad.net/openstack-manuals/+spec/api-samples-to-api-site
  Moving content to project repos would be the opposite moving direction
  and may work perfectly well for this use case.

* https://blueprints.launchpad.net/openstack-manuals/+spec/api-try-it-out
  I'd see this as a stretch goal, not necessarily required for the main
  goal of making contributions and maintenance better going forward.

Additional information:

* API Archaeology: Complexity and sizing of an interface
  http://justwriteclick.com/2015/01/12/api-archaeology-complexity-and-sizing-of-an-interface/
  This blog post gives counts as of the January post date. Aas of April 27,
  2015 the counts are now 915 calls.
* List of services with REST APIS:
  http://git.openstack.org/cgit/openstack/governance/tree/reference/projects.yaml

* Issues with WADL2Swagger (really the underlying issue is that Swagger
  definitions itself requiring JSON schema to be useful and contractual)
  https://github.com/rackerlabs/wadl2swagger/issues/8

* November 2014 User Survey Data (will add April 2015 when available) http://superuser.openstack.org/articles/openstack-user-survey-insights-november-2014
