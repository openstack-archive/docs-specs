..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==================================
Publish stable release translation
==================================

https://blueprints.launchpad.net/openstack-manuals/+spec/publish-stable-translation

Add the feature of publication of translated documents for stable release.

Problem description
===================

Currently, Some documents such as Installation Guide have versioned documents.
On the other hand, Translation feature works on master branch only.
So, I18n team can not publish the documents for stable release.

Proposed change
===============

Change translation target from all documents to versioned documents
on stable branch so that translation resources for only versioned
documents are uploaded to Zanata.
Also, execute translation related Jenkins jobs on stable branch.
Translation target are:

* Installation Guide for Liberty
* common-rst

Alternatives
------------

* Don't publish the translation guides for stable release.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* KATO Tomoyuki (to222)

Work Items
----------

* Update the ``doc-tools-check-languages.conf`` file to
  change translation resources on stable branch.
* Create branch on Zanata server for repositories.

Dependencies
============

The main dependency is on docs.openstack.org infrastructure updates.

Testing
=======

Testing will follow the standard documentation and translation
review processes.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-i18n, the openstack-i18n mailing list,
  `I18n team meeting`_, and `Mitaka Design Summit Etherpad`_.

  .. _`I18n team meeting`:
     https://wiki.openstack.org/wiki/Meetings/I18nTeamMeeting

  .. _`Mitaka Design Summit Etherpad`:
     https://etherpad.openstack.org/p/tokyo-i18n-meetup
