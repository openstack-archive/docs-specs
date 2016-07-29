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
some many moving parts and different usecases. People trying to deploy,
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
  None

Work Items
----------

* Remove generic terms and acrynoms from the glossary
* Add links to the install guides for relevant terms
  * either on a per-book or a per-term basis
* (Optional) Add additional terms

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
