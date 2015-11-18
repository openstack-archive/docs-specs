..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================================================
Add Messaging Service(zaqar) to the Config Reference
========================================================

Launchpad blueprint:

https://blueprints.launchpad.net/openstack-manuals/+spec/zaqar-config-ref

Messaging service(zaqar) should be added to the Config Ref similar to
the other OpenStack services.


Problem description
===================

Messaging service(zaqar) is not currently included in the
Configuration Reference. The related content is currently kept in-tree
in the zaqar devref. Administrators using messaging service would expect to
find a reference document from the official Configuration Reference. The
automated configuration doc tools should be leveraged.


Proposed change
===============

The content would be similar to the other services in that it would have
sections to describe introduction, backends, log files, and options.

Automatically generated configuration tables should be used where possible.


Alternatives
------------

N/A

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Fei Long Wang (flwang)

Other contributors:
  Existing docs from zaqar in-tree devref.

Work Items
----------

* Messaging service chapter
* Generated configuration file tables


Dependencies
============

Now the conversation to RST is ongoing, so it would be better to get this in
once that's done.


Testing
=======

Review by the Zaqar core team and contributors.

References
==========

Zaqar devref:

* http://docs.openstack.org/developer/zaqar/index.html
