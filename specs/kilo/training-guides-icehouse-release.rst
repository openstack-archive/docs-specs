..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Icehouse release for training guides
====================================

Include the URL of your launchpad blueprint:

https://blueprints.launchpad.net/openstack-training-guides/+spec/icehouse-release

Training guides is ready to release Icehouse content. As per our discussions
during the Kilo design sessions in Paris, the team came to a common conclusion
to transition from XML books to RST presentations for delivering training
content more efficiently and to eliminate duplication of the content.

Advantages:

- Easy to transition from XML to RST.
- XML content will still be accessible for the current training sessions.
- Repetation of content from the manuals repository will be eliminated.
- Easier to get in track with the current release cycle of OpenStack.

Note: Etherpad discussions for Kilo summit:
https://etherpad.openstack.org/p/training-guides-kilo-summit

Problem description
===================

A detailed description of the problem:

* XML content is to be deleted.
* Migrate from XML book format to RST presentation format.
* Keep the existing content for supporting on-going training sessions.


Proposed change
===============

* Freeze the master branch and branch it for Icehouse.
* The XML content will reside in the Icehouse branch for training guides.
* There will be no XML content in the master branch after the release.
* Master branch will only contain RST files.


Alternatives
------------

* Keep XML and RST files side by side.

This alternative is not advisable as it has multiple issues with XML
cross-referencing and should be avioded at all costs.


Implementation
==============

Assignee(s)
-----------

dguitarbite

Work Items
----------

* Freeze master branch for training guides repository.
* Branch the master branch and name it as Icehouse.
* Delete the XML content in the current master branch.

Dependencies
============

None.

Testing
=======


References
==========

https://etherpad.openstack.org/p/training-guides-kilo-summit
