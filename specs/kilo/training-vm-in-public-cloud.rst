..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===========================
Training VM in public cloud
===========================

https://blueprints.launchpad.net/openstack-training-guides/+spec/training-vm-in-public-cloud

Make the training cluster work in public clouds, with node VMs running as
instances.


Problem description
===================

The current lab-scripts work on computers running Linux, Mac OS X, and
Windows. They need at least 4 GB RAM and about 10 GB of hard disk space.

Some students may not have access to such a system, or running the scripts
may be too difficult or time-consuming for them. In these cases, being
able to give them access to a training setup hosted in the cloud could
be a useful alternative.


Proposed change
===============

Presumably the most simple (and therefore most realistic) method of
achieving the goal is to find and document a method of producing a
VM that can be imported into the OpenStack Image Service and used by
OpenStack Compute.

A multi-node setup is unlikely to work without major changes that a)
will take time to implement and b) may result in a setup and/or behavior
that differs substantially from a real OpenStack cluster.

Therefore, an all-in-one VM is proposed. Last time it was tested,
running all client-scripts within the same VM seemed to yield a
working all-in-one OpenStack system.

Some adjustments will likely be necessary to make the serial console
(nova console-log), noVNC, and networking work.

If the proposed change is successfully implemented, the training-guides
project might offer instructions, an automated script for building this
special VM, and/or the resulting VM for download.

Alternatives
------------

The lab-scripts could be optimized to reduce even further the resources
necessary to run the scripts. Vast improvements, however, are unlikely, and
script performance on low-spec machines may never be sufficient.

Data model impact
-----------------

None

REST API impact
---------------

None

Security impact
---------------

The VMs as produced by the scripts use known default passwords and
insecure ssh keys. They are reasonably secure only if external access
to the VMs is not possible. Put differently: they are about as secure
as a standard CirrOS image.

Anyone setting such a VM up for training should know how to prevent
unauthorized access.

Notifications impact
--------------------

None

Other end user impact
---------------------

As mentioned above, the experience of a system hosted on OpenStack
will differ considerably from a training cluster running on a user's
machine. Training will have to take the differences into account.

Performance Impact
------------------

None

Other deployer impact
---------------------

None

Developer impact
----------------

This feature could probably be implemented without affecting the rest of
lab-scripts (much). However, if an all-in-one cluster were to become a
first-class feature, we might have to reconsider some of the scripts that
currently happen to work although they expect to run on separate nodes (and,
for instance, overwrite existing configuration).

Depending on the solution, keeping this feature up-to-date with development
will take some effort.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  None

Other contributors:
  None

Work Items
----------

- proof of concept (POC) all-in-one training VM
- import into glance, launch instance
- make serial and noVNC consoles work
- fix network access
  - to/from node VM
  - to/from instance running within node VM
- documentation for end-users


Dependencies
============

* We need access to an OpenStack installation for development and
  testing. Whereas the final solution should not require admin rights,
  admin access might be useful when prototyping this kind of setup.

* If we want to host the VM images, we need a hosting provider.


Testing
=======

Regression testing for this feature (once it is implemented) will not be
automated, at least in the foreseeable future.


Documentation Impact
====================

The differences in setup and behavior are likely to have an impact on
the training slides and hands-on exercises.


References
==========

* Spec requested in training-guides meeting, 2014-11-17
  http://eavesdrop.openstack.org/meetings/training_guides/2014/training_guides.2014-11-17-17.00.log.html
