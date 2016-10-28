..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=========================
Training-labs Python port
=========================

https://blueprints.launchpad.net/openstack-manuals/+spec/labs-python-port

Training labs was originally written in Bash. But it has grown from a simple
set of scripts to a full blown project. Moving to a modern interpreted
programming language is the next logical step. Hence, rewriting training-labs
in Python allows us to increase the agility, quality and features supported.

Python is an obvious choice. It is a programming language which should cater
the current demands, features while being the language of the OpenStack
community. Python is shipped by default on Mac OS X and Linux platforms.

Problem description
===================

Training labs is growing with ever increasing features and complexity. There
is a demand from users to add support for more features and plugins like
Public Cloud support. Moving to a modern programming language addresses
many inherent limitations of Bash for the given use-cases. The following
short comings, new feature demands are listed below which explain the need
for this rewrite.

* Adding new functionality like public cloud support (AWS, GCE, RackSpace).

* Providing better support for Windows platform.

* Using better configuration format.

* Supporting multiple architectures for OpenStack.

* Reducing the complexity for better testing, bug fixing, and more.

* Better support for new features like PXE booting.

* Providing proper modularity and abstraction for the host side scripts.

Proposed change
===============

Rewriting the host side scripts in Python. Host side scripts carry out tasks
to orchestrate the hypervisors (KVM/VirtualBox) and manage virtual networks,
provide logging, inject guest side scripts etc.

Initially, we plan to introduce Python scripts in parallel with existing Bash
scripts to eliminate the impact of this change to the end-users. Once the
Python port is tested, we will remove the host side Bash scripts. At this
point the end-users will invoke training-labs via Python. The impact to the
end-users is minimal to zero.

This is a major rewrite of the project and should impact the entire project
itself. But the migration plans provide a safe way to implement this change
and have minimal impact.

Alternatives
------------

* Use similar programming language like Ruby, Go Lang, etc.

* Improve the architecture and add relevant features to Bash.

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  Roger Luethi <rl@patchworkscience.org>

Other contributors:
  Pranav Salunke <dguitarbite@gmail.com>

Work Items
----------

* Initial one to one rewrite to Python.

* Improve and refactor the python code.

* Remove older host side code (Bash code).

Dependencies
============

* None

Testing
=======

Mostly manual testing in the initial phases. During the latter part of the
implementation, the CI system should also carry out automated testing.

References
==========

None
