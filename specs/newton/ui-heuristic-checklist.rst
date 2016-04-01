..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===============================================
Add UI heuristic checklist to Contributor Guide
===============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/ui-heuristic-checklist

Add an OpenStack UI heuristic checklist within the OpenStack
Documentation Contributor Guide under the UI guidelines section.

Problem description
===================

The OpenStack UX project is interested in adding a section to the
OpenStack Documentation Contributor Guide that provides a
graphical user interfaces (GUI) heuristic checklist developed by the
OpenStack project teams. The content is connected to the UI text
guidelines we published for Mitaka.

Heuristic evaluations are a simple inspection method that allows
engineers and designers to review designs for common usability issues.
The benefits are that heurisitcs are low-cost and relatively easy to use
for individuals that are evaluating a design.  An additional benefit of
heurisitics is that they help maintain consistency and transparency in how
multiple designs are reviewed.

An example of a heuristic includes the "10 Usability Heuristics for
User Interface Design" developed by Jakob Nielsen in the 1990's that
includes principles for error recovery and system status.  The OpenStack
community heuristic includes principles that are specific to developing
for the cloud and inlcude a focus on designing to scale along with examples
such as the number of images within a typical production deployment.

The working draft of these guidelines is in progress and can be viewed
here: https://etherpad.openstack.org/p/mitaka-openstackux-heuristic

The value of this effort is to help provide an improved
usability for operators, admins, and end users by creating
tools that help promote consistency in OpenStack GUI interfaces.

Proposed change
===============

In a new UX/UI section of the contributor guide, add a topic for the
UI heuristic checklist. The heuristic checklist could be
added as a peer to both the UI text guidelines (already exist) and to
the (proposed) UX personas section within the OpenStack
Documentation Contributor Guide.

Proposed table of contents:

UX/UI guidelines (section title updated to reflect broader scope)

* Value/Intro
* UI text guidelines (already exist)
* UI heuristic checklist (new, proposed by this spec)
* UX personas (new, proposed in separate spec)

Alternatives
------------

#. Do not add UI heuristic checklist.
#. Add checklist, but create it in a new guide for UX design.
   An email was distributed to the doc project regarding
   the idea of a new UX design guide to house UX-related
   resources and tools for a cross-project audience.
   These were the options discussed in the email, sent 3/7/16.
   Please see email for more detail and history.

   Option A
    Create a OpenStack UX Design Guide: Tools for
    developers guide, under the Contributor Guides section
    on docs.openstack.org. The guide would house UX design materials,
    like engaging UX, personas, use cases, resources section with
    heuristic checklists, etc. Basically, creating a design corner
    concept with guide name tbd.

    * Pros: Peer to other contributor guides - creates a more
      prominent focus on UX/UI design in OpenStack, we could reference
      guide from appropriate locations to increase visibility
    * Cons: New guide - logistics more complicated, logistics help needed
      Takes longer to get reviews going

   Option B: Add to the existing Doc Contributor Guide, but modify the
    guide's scope.

    * Pros: Existing guide - logistics easier, content would be available
      to review sooner UI guidelines content in one location
      (The new UI heuristic checklist links to the UI text guidelines
      that we recently added to the doc contributor guide.)
    * Cons: Not just for text guidelines anymore, so the guide's current
      scope would expand slightly to include a section specifically on
      UX/UI tools for a cross-project audience.

   Option C: Add to the existing Doc Contributor Guide as-is,
    potentially adjust later...

    * Pros: Content available for review quickly, lowest logistical
      impact
    * Cons: scope could be confusing for users, adjusting later
      delays some work

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
* rcresswe@cisco.com

Work Items
----------

* Reach a consensus on new section's location and content structure.
* Identify new topics to be created and submit content/reviews using the
  [blueprint ui-hueristic-checklist] tag.

Dependencies
============

This work is a collaboration between the UX and Doc team that requires
UX project team input and creation of the heuristic checklist.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with
  [ui-heuristic-checklist] in the subject.

  .. _`documentation team meeting`:
     https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting



