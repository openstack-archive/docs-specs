..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

============================================
OpenStack Liberty Installation Guide: Debian
============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/installguide-liberty

The OpenStack Installation Guide for Debian requires a number of changes
and updates before it can be published to the OpenStack documentation site.

Problem description
===================

The following steps need to be taken before the OpenStack Installation Guide
for Debian can be re-published:

* Conversion to RST
* Testing and revision of content


Proposed change
===============

#. Convert the Debian part of Installation Guide to RST.

#. Use ifconfig Sphinx extension http://sphinx-doc.org/ext/ifconfig.html to specify the conditional for Debian content using 'debian-based' tag according to the main specification http://specs.openstack.org/openstack/docs-specs/specs/liberty/installguide-liberty-rst.html.

#. While RST migration will be going on, test the guide and report bugs on launchpad. 

#. Prepare the drafts to fix the bugs.

#. Once migration is done, put fixes on review.

#. Once updated, raise a discussion to publish Debian Installation Guide on docs.openstack.org.


Alternatives
------------

None

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  aadamov

Other contributors:
  karin-levenstein

Experts:
  thomas

Work Items
----------

* Test the guide.
* Report bugs.
* Write fixes.
* Convert to RST Debian specific parts (in parallel with testing the Guide).
* Put fixes on review.
* Publish the guide on the main page.


Dependencies
============

The main dependency is on the main installation guide conversion described in http://specs.openstack.org/openstack/docs-specs/specs/liberty/installguide-liberty-rst.html.


Testing
=======

The sames procedures as specified in http://specs.openstack.org/openstack/docs-specs/specs/liberty/installguide-liberty-rst.html.

References
==========

Discussion can occur using any official medium including IRC in #openstack-doc, the openstack-docs mailing list with [install-guide][debian] tags in the subject, weekly `Installation Guide specialty team meeting <https://wiki.openstack.org/wiki/Documentation/InstallGuide>`_, weekly `documentation team meeting <https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting>`_, and potentially etherpads.

In addition, Debian Installation Guide meetings can be arranged on Mondays at 13.00 UTC in Google Hangout to discuss the blocking issues.
