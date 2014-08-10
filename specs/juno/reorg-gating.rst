..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Reorganization of gating setup
==========================================

https://blueprints.launchpad.net/openstack-manuals/+spec/reorg-gating

Reorganize the gating setup to combine the tiny jobs into a single
voting and a single non-voting check. This will give more flexibility
in adding new jobs and reduce load of Jenkins.

Problem description
===================

Most of the current jobs are very small and it takes far longer to
setup the virtual environment than running the tests. For example the
niceness check runs in two seconds - while Jenkins needs at least 3
minutes for the whole job. The difference is that Jenkins needs to
start a new virtual machine, install the git repository and all
packages.

With the addition of checking for links, we would have the following
tiny jobs where each normally runs in less than 2 seconds:
* niceness check
* syntax check
* deletions check
* linked URL check

Let's combine these tiny jobs into voting and non-voting jobs.

This gives us also the flexibility to add additional jobs easily and
decide per repository on which of these jobs are voting and which are
non-voting.

Proposed change
===============

Use the following voting gate and check jobs:
* checkbuild - no change
* check-voting - includes niceness, syntax, deletion checks

Additional use the following non-voting check job:
* check-non-voting - check validaty of linked URLs
* checklang - no change


Alternatives
------------

* Add an additional non-voting check for linked URLs

* Add the checklang job also to non-voting. I suggest to not do it
  since these jobs are two different kinds of jobs and here the
  differentiation helps.


Implementation
==============

This will be done with enhancing tox.ini with new tests and changing
the jobs in Jenkins.


Assignee(s)
-----------
jaegerandi (Andreas Jaeger)


Work Items
----------
* Add new jobs to tox.ini for all documentation projects
* Update Jenkins jobs in openstack-infra/config repository
* Remove now obsolete jobs from tox.ini in all documentation projects

Dependencies
============

* Release of openstack-doc-tools with the linked URL check


Testing
=======

The tox.ini changes will be tested manually.


References
==========
