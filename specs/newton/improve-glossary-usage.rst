..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Improve usage of glossary in manuals
====================================

Include the URL of your launchpad blueprint:

https://blueprints.launchpad.net/openstack-manuals/+spec/improve-glossary-usage

There are 712 terms defined in the glossary.
There are 165 references to the glossary terms throughout the
openstack-manuals repo.

The glossary exists to explain terms in the context of OpenStack, so that users
don't have to look up terms that they are unfamiliar with and try to fit it
back into the right context.

This is only useful if:
- users can easily access the glossary (i.e. link to glossary in docs).
- the glossary is not over burdened with acrynoms or terms that are not
specific to OpenStack


Problem description
===================

OpenStack is a large project, with many different components and use cases. One
major issue that people have when trying to set up OpenStack is that there are
so many moving parts and different use cases. People trying to deploy,
configure and use OpenStack aren't necessarily going to be familiar with all
the components, technologies or terminology associated with OpenStack.

There is a glossary which accompanies the OpenStack manuals, which provides
definitions for many of these terms. However, there is relatively little
reference to this useful resource in the manuals, so users/deployers may not
be aware of the existance of the glossary, and spend time looking up these new
terms only to have to fit them back into the context of OpenStack, which might
be a new concept to them. This can lead to OpenStack being perceived as
difficult to grasp, and hard to ramp up on.


Proposed change
===============

The proposed change would add links to glossary terms in the manuals so that
users can easily access descriptions of unfamiliar terms within the context of
OpenStack. This is so that users have a better experience and can come to terms
with OpenStack terminology quicker than if they had to look up the term and
figure out how it relates to/is used in OpenStack.

There are two step in this process (with multiple sub steps):
* Remove acronyms/generic terms
* Link terms from the glossary to the books

**Step 1: remove acronyms/generic terms**
--------------------------------------

The first step is removing unnecessary terms from the glossary.
In order to achieve that, we'd need to decide what the unnecessary terms were.
This is likely to be time consuming in terms of reviews. In terms of proposed
removals, the suggested method is:

* Identify criteria for removal:
   * Acronyms
   * Generic terms (terms defined in the glossary should include HOW they are
     related to OpenStack)
* Propose patches for each set of criteria in alphabetical chunks:
  - e.g. [glossary] Remove acronyms [A-B]

**Acronyms** are the easiest place to start
An acronym shouldn't have a definition of it's own, it should be part of the
relevant entry::
     # Good entry, the commonly used acronym is included in the entry heading
     IP Address Management (IPAM)
     The process of ....

     # this entry is bad because it just expands the acronym
     IPL
     Initial Program Loader.

An entry that passes the first test doesn't necessarily get trough on round two,
but it keeps things clean as the content is refactored.

For determining generic terms to remove, valid terms must be defined. Any term
falling outside the criteria of valid is up for removal.

A **valid term** is:
* Specfic to OpenStack e.g. *tennant*, *project*, *compute node*
  This is a term that doesn't exist or is used in a different way outside of
  OpenStack.
* Codename for a project e.g. *nova*, *neutron*, *keystone*
  In these cases, the code name is the entry, and the service is not::
    ::
    # This is an unnecessary entry, because the term readers would be looking
    # for is Trove, not database service
    Database Service
    ... The project name of Database service is trove.
  * In most occurances, the service name/code name can be combined into a
    larger entry.

* Generic terms, defined in the context of its usage in OpenStack
 * Supported technologies are not valid, as this would be clear from the
    manuals where it is mentioned (same is true for drivers)
    * Exception: the technology is used in a non-standard way
  * Litmus test: Will an internet search return the same information?
  ::
  # Bad - technology used in OpenStack, in a standard way
  SQL-Alchemy
  An open source SQL toolkit for Python, used in OpenStack.

**Step 2: Link terms from the glossary to the books**
The second part of this change is to make sure the glossary is used. This step
links relevant terms from the manuals to the glossary entries.
This can be done on a per-book basis in the following way (depending on the
size of the book and the number of terms):

* Iterate through the glossary terms and determine whether they are used in the book
* Group the terms into managable chunks::
  [glossary] admin-guide links [A-D]
* Only the first occurance in a chapter should be linked

**Review process**
For straightforward reviews, each set of changes is proposed for removal.
If there are any contentious terms, these will be revoced from the main review,
and proposed individually, so that most of the work can take place as quickly
as possible, and not get blocked because there are strong opinions about an
exceptional term.

Alternatives
------------

None

In this case, all the parts are present, but they have to be better
connected/accessible.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
 emma-l-foley

Other contributors:
  TBD

Work Items
----------

- Clean up the glossary
  - Remove acronyms
  - Remove unneccessary/generic terms
- Improve usage of the glossary
  - Add links to each book

Dependencies
============

None

Testing
=======

No additional testing should be required.

The ability to check if a glossary term exists is already present, and can be
used to ensure that there are no invalid links.

References
==========
Mailing list thread:
  http://lists.openstack.org/pipermail/openstack-docs/2016-July/008915.html
