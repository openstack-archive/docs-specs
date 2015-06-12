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

#. Because of the similarity between Debian and Ubuntu, most Debian users can
   follow the Ubuntu installation instruction. Most Debian-specific
   configuration content is expected to be maintained in the Debconf chapter.

   .. note::
      The debconf system is the general interface between Debian and its user.
      It is used to change configuration directives of OpenStack services.
      However, we understand that the goal is not to just teach how to install
      OpenStack, but also to understand what should be configured in which
      directive of what section of what file. Therefore, the Debconf chapter
      will include explanations of the directives that the Debian
      packages handle automatically.

      In the Debconf chapter we will tell users about debconf prompts with
      screenshots of what it configures, so that it can be later used either
      using pre-seeding or through puppet scripts. So, for every debconf
      prompt, we shall document what directive it influences, which means
      Debian readers will also get the same level of learning.

      To ensure that Debian users get the same level of understanding as other
      users, the Debconf chapter will document the following elements:

      * Debconf prompts
      * The directive influenced by the prompt
      * Screenshots showing the configuration results
      * Note that this information can be used for pre-seeding and puppet
        scripts as well.

#. Convert the Debconf chapter of Installation Guide to RST.
   This chapter describes the following procedures:
   * Setting up databases
   * RabbitMQ credentials (login, pass, host)
   * [keystone_authtoken] (login, pass, tenant and host)
   * API endpoints

   .. note::
      These need to be in a single chapter, to avoid repeating the same
      content for each service.

#. Use a `debian` tag to specify the conditional for Debian content
   according to the main specification:
   http://specs.openstack.org/openstack/docs-specs/specs/liberty/installguide-liberty-rst.html
   You can find added tags here:
   https://review.openstack.org/#/c/191516.

#. While RST migration will be going on, test the guide and report
   bugs on launchpad.

#. Prepare the drafts to fix the bugs.

#. Once migration is done, review the fixes.

#. Once updated, raise a discussion to publish the Debian Installation Guide
   on docs.openstack.org.


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

The main dependency is on the main installation guide conversion described in
http://specs.openstack.org/openstack/docs-specs/specs/liberty/installguide-liberty-rst.html.


Testing
=======

The sames procedures as specified in
http://specs.openstack.org/openstack/docs-specs/specs/liberty/installguide-liberty-rst.html.

References
==========

Discussion can occur using any official medium including IRC in
#openstack-doc, the openstack-docs mailing list with
[install-guide][debian] tags in the subject,
weekly `Installation Guide specialty team meeting
<https://wiki.openstack.org/wiki/Documentation/InstallGuide>`_,
weekly `documentation team meeting
<https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting>`_,
and potentially etherpads.

In addition, Debian Installation Guide meetings can be arranged on
Mondays at 13.00 UTC in Google Hangout to discuss the blocking issues.
