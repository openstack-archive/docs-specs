..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============================================
Add UI content guidelines to Contributor Guide
==============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/ui-content-guidelines

Add a new section describing UI content guidelines within the OpenStack
Documentation Contributor Guide.

Problem description
===================

The OpenStack UX project is interested in adding a section to the
OpenStack Documentation Contributor Guide that provides guidance
on maintaining consistent structure, style, and syntax for any
graphical user interfaces (GUI) developed by the OpenStack project teams.
The guide could be applied to IA efforts for the panel headings,
modal headings, modal section headings, section descriptions, labels, etc.

The value of this effort is to help provide an improved
usability for operators, admins and end users.

Proposed change
===============

Add a section to address UI content guidelines.
This UI content guidelines section could be
added as a peer to the Writing Style section within the
OpenStack Documentation Contributor Guide.
Proposed table of contents:

* Value/Intro
* Capitalization guidelines for text in UI

  * Examples of sentence-style capitalization
  * Examples of headline-style capitalization
  * Common UI elements/headings that use sentence-style capitalization
  * Common UI elements/headings that use headline-style capitalization
  * UA Cheat Sheet (visually show style in an image)
* Common action labels (i.e. Cancel, Add, Close, Delete, etc...), other
  common labels (i.e. IP address)
* Refer to user interface elements consistently (link to ui-terminology.html)
* Follow writing style guidelines (link to page in contributor guide)
* Error message guidelines (structure, clarity, completeness)

  * Structure definitions
  * Examples

Alternatives
------------

- Do not add UI content guidelines.
- Add guidelines, but create a new guide.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

* pkruithofjr@gmail.com
* stemke@us.ibm.com

Other contributors:

* gmolson@us.ibm.com
* nancy.ann.michell@hpe.com
* openstack@lanabrindley.com

Work Items
----------

* Reach a consensus on new section's location and content structure.
* Identify new topics to be created and submit content/reviews using the
  [blueprint ui-content-guidelines] tag.

Dependencies
============

This work is a collaboration between the UX and Doc team that requires
input from both projects.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with
  [ui-content-guidelines] in the subject.

  .. _`documentation team meeting`:
     https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting



