..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

====================================
Icehouse release for training guides
====================================

https://blueprints.launchpad.net/openstack-training-guides/+spec/training-icehouse-release

Training guides is ready to release Icehouse content. As per our discussions
during the Kilo design sessions in Paris, the team came to a common conclusion
to transition from XML books to RST presentations for delivering training
content more efficiently and to eliminate duplication of the content.

Advantages:

- Easy to transition from XML to RST.
- XML content will still be accessible for the current training sessions.
- Repetation of content from the manuals repository will be eliminated.
- Easier to get in track with the current release cycle of OpenStack.
- Maintain release cycle in sync with openstack releases.

Note: Etherpad discussions for Kilo summit:
https://etherpad.openstack.org/p/training-guides-kilo-summit

Problem description
===================

A detailed description of the problem:

* XML content is to be archived and deleted.
* Migrate from XML book format to RST presentation format.
* Keep the existing content for supporting on-going training sessions.
* Publish current XML content to Icehouse branch only.
* Other releases like Juno, Kilo will be published using RST based slides.
* In future Juno, Kilo branches will be created as required for publishing the
  newer releases for training guides.


Proposed change
===============

* Freeze the master branch and branch it for Icehouse.
* Add Icehouse watermark to the XML content.
* The XML content will reside in the Icehouse branch for training guides.
* XML content will not be under active development and mostly for archival
  purposes for supporting ongoing training sessions using the current content.
* There will be no XML content in the master branch after the release.
* Master branch will only contain RST files.


Alternatives
------------

* Use git history to point to the given Icehouse release instead of branch.
  This has multiple issues:
  - It may create confusion for trainers (our end-users).
  - This will only serve the developers of this project.
  - Difficult to publish newer releases.
* Keep XML and RST files side by side.
  - This alternative is not advisable as it has multiple issues with XML
  cross-referencing and should be avioded at all costs.


Implementation
==============

Assignee(s)
-----------

dguitarbite

Work Items
----------

* Freeze master branch for training guides repository.
* Create a stable/icehouse based on the current master branch.
* Update docs.openstack.org/icehouse/index.html page to point to
  training-guides/icehouse
* Change publish process in icehouse branch (pom.xml, tox.ini) in the
  /icehouse branch.
* Remove current content from /training-guides master branch.
* Add redirects from /training-guides/icehouse to trunk/icehouse
* Change publish process in training-guides/master to publish to trunk/master to
  include build results of the RST content.
* Update docs.openstack.org/trunk/index.html page in master branch to include
  build results of the RST content.

Dependencies
============

None.

Testing
=======


References
==========

https://etherpad.openstack.org/p/training-guides-kilo-summit
