..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

========================
Use Case Collection Form
========================

Problem description
===================

The OpenStack user and operator community want to be able to provide input 
for use cases to help provide direction for OpenStack projects and provide 
possible usage models for the architecture guide. The current methods of 
using either the dev-list or through blueprints can be quite daunting to 
newcomers and non-developers.

We need to a simple way for operators to provide input and collect feedback.


Proposed change
===============

The proposal is to create a web form to collect use cases and user stories,
the output from the form can then be categorised by keyword and presented
in a blog post style, allowing for further questions to be asked or other
comments. 

The form would need to include input fields to collect the following:

      #. Summary
      #. Detailed breakdown
      #. General Notes
      #. Related Project (optional)
      #. Theme
      #. Release
      #. Company (optional, but highly desired)
      #. Email Address

The number of input fields could be extended, but we should keep in mind that
we want to make it simpler for people to provide input.

The intention is make this a living process to support input and information
gathering. 

A simple voting mechanism that allows other operators to indicate that they 
have the same use case would also be useful.

Alternatives
------------

Create a google form.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  * 

Other contributors:
  * shaunom

Work Items
----------

  * Reach a consensus on the form requirements
  * Create the web from
  * Create the blog page mechanism


Dependencies
============

None

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with [use-case-form]
  in the subject, biweekly Ops Guide specialty team meeting,
  weekly documentation team meeting, and potentially etherpads.

* This related to a discussion held during the Ocata Docs planning session
  in Barcelona.

.. _`Ocata Planning  etherpad`: https://etherpad.openstack.org/p/BCN-Docs-OcataPlanningWG
