..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===========================
Publishing of draft manuals
===========================

https://blueprints.launchpad.net/openstack-manuals/+spec/draft-publishing

Problem description
===================

Currently, the following guides are not published at all from the
master branch of the git repository:

* Networking Guide
* Install Guide
* RST User Guides (will change while we discuss this spec)

This makes it difficult for contributors to review current status.

We publish the Configuration reference to
http://docs.openstack.org/trunk/ .

We also have a trunk index page that speaks about "Draft" guides but
references also continous publishing guides which might confuse users.

Proposed change
===============

#. Publish draft content to a special location like `/draft/`.
#. Create a single page that references all draft documents and only
   those, this page should be hidden.
#. Remove the current `trunk/index.html` page and links to it.
#. Take care that search machines do not index these pages.
#. Ensure that any partial translated pages do not publish to `/lang/trunk/`
   but instead to `/lang/draft`.

Alternatives
------------

#. Keep status quo
#. Publish to another location like `/trunk/`.

Implementation
==============

* Change location of publishing.
* Remove `trunk/index.html` and links to it.
* Regenerate sitemap.
* Add `/draft/` to :file:`robots.txt`.

Assignee(s)
-----------

jaegerandi

Work Items
----------

See implementation.

Dependencies
============

None.

Testing
=======


References
==========

http://lists.openstack.org/pipermail/openstack-docs/2015-April/006243.html
