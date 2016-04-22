..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============================================
Add UI content guidelines to Contributor Guide
==============================================

https://blueprints.launchpad.net/openstack-manuals/+spec/ux-personas

Add OpenStack personas within the OpenStack
Documentation Contributor Guide under the UI guidelines section.

Problem description
===================

The OpenStack UX project is interested in adding a section to the
OpenStack Documentation Contributor Guide that describes personas
developed by the OpenStack UX project team.

The personas could be applied to development design decisions,
used as IA resources for evaluating requirements for new/changed
guides, and in possible marketing collateral.

The value of this effort is to help provide developers,
designers, and reviewers with an improved awareness
of OpenStack users to design and develop OpenStack with
the appropriate audience goals, and resulting task flows, in mind.
Personas help establish consistency across projects, create increased
awareness for the customer and their goals, as well as,
communicate differences between customers.

Proposed change
===============

In a new UX/UI section of the contributor guide, add a topic
collection for personas. The personas section could be
added as a peer to both the UI text guidelines (already exist) and to
the (proposed) UI heuristic checklist section within the OpenStack
Documentation Contributor Guide.

Proposed table of contents:

UX/UI guidelines (section title updated to reflect broader scope)

* Value/Intro
* UI text guidelines (already exist)
* UI heuristic checklist (new, proposed in separate spec)
* UX personas (new, proposed by this spec)

In the personas section, the following personas will be ellaborated
upon.

Cloud Personas
~~~~~~~~~~~~~~

The personas information will be based upon model companies and
their ecosystems. They describe the cloud adoption stages and
describe multiple roles defined with each company. Roles that
perform similar tasks may be called something different in each
company. It is also common for the same person to perform
multiple roles or shared tasks. Early research
shows that the role ecosystem is complex and diverse.

Contact Piet Kruithof for the most recent version of
the personas.

Alternatives
------------

#. Do not add UX personas.
#. Add personas, but create them in a new guide for UX design tools.
   An email was distributed to the doc project regarding
   the idea of a new UX design guide to house UX-related
   resources and tools for a cross-project audience. These were
   the options discussed in the email (sent 3/7/16). Please see email
   for more detail and history.

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
    * Cons: New guide-logistics more complicated, logistics help needed
      Takes longer to get reviews going.

   Option B
    Add to the existing Doc Contributor Guide, but modify the guide's scope.

    * Pros: Existing guide-logistics easier, content would be available
      to review sooner UI guidelines content in one location.
      The new UI heuristic checklist links to the UI text guidelines
      that we recently added to the doc contributor guide.
    * Cons: Not just for text guidelines anymore, so the guide's current
      scope would expand slightly to include a section specifically on
      UX/UI tools for a cross-project audience.

   Option C
    Add to the existing Doc Contributor Guide as-is, potentially adjust later.

    * Pros: Content available for review quickly, lowest logistical impact.
    * Cons: Scope could be confusing for users, adjusting later delays
      some work.

Implementation
==============

Assignee(s)
~~~~~~~~~~~

Primary assignee:

* pkruithofjr@gmail.com
* stemke@us.ibm.com

Other contributors:

* gmolson@us.ibm.com
* nancy.ann.michell@hpe.com
* openstack@lanabrindley.com
* rcresswe@cisco.com
* jamielennox@gmail.com
* jacalcat@us.ibm.com

Work Items
~~~~~~~~~~

* Reach a consensus on new section's location and content structure.
* Identify new topics to be created and submit content/reviews using the
  [blueprint ux-personas] tag.

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
  [ux-personas] in the subject.

  .. _`documentation team meeting`:
     https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting

