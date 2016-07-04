..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

=====================
Improve UI guidelines
=====================

https://blueprints.launchpad.net/openstack-manuals/+spec/ui-guidelines

To create a new patterns library for OpenStack projects that use
graphic user interfaces (GUI).

This will be a non-prescriptive set of guidelines for developers to
follow. This project aims to to weave a thread of consistency throughout
GUI related projects where there has previously been none.

This spec aims to open up the discussion between all projects, to ensure that
this is being addressed appropriately and is an effective measure to assist
in closing the gap between OpenStack projects.

.. note::

   Originally there was a plan to create a heuristic
   (https://etherpad.openstack.org/p/mitaka-openstackux-heuristic), but
   this has been scrapped.


Problem description
===================

Operators are upset about the lack of consistency across (and even within)
OpenStack GUI projects.

This is a pain point for the community as there are several projects that
have a GUI, including Horizon, Fuel, Ironic, Murano, Mistral among others
with limited consistency amongst them.


Proposed change
===============

Adding new content, and revising old content, in the UX/UI section of
the OpenStack Documentation Contributor Guide:
http://docs.openstack.org/contributor-guide/ui-text-guidelines.html

This section will provide principles for developers producing new
content. The aim is to make it easy to follow the suggested patterns,
ensuring that defining the GUI conventions will drive consistency
between projects.

The update to the OpenStack manuals UI Guidelines will determine patterns
that currently exist, and create new patterns where there are gaps in
knowledge. For example, information on how to phrase help text, what type
of error to display, and they way we alert users, and so on.

Currently suggested topics (please suggest others):

* Use Bootstrap
   * Existing components over custom components
   * Keep responsive grid in mind
   * SCSS - Use Existing Variables, no hardcoding any values, this includes pixel
     values, colors, zindex, etc
* Patterns
   * Alerts
      * Inside of a Modal (form alert)
      * Outside of a Modal (growl / toast)
      * What are the cases when I should use a ‘success’, ‘info’,
        ‘warning’ or ‘error’?
   * Horizon Specific Controls
      * Checkboxes —> use Themable Checkboxes in lieu of standard checkboxes
      * Selects —> use Themble Selects in lieu of standard selects

Alternatives
------------

* Agree on patterns amongst each of the projects, and document these patterns
  in the developer documentation for each project.

* Leave things as they are.


Implementation
==============

Assignee(s)
-----------

Primary assignee:
  * Alexandra Settle <asettle>

Other contributors:
  * Eddie Ramirez <ediardo>
  * Ankur Gupta <ankur-gupta-f / ankur-gupta-f1>
  * Alex Sulgrove <@alexsulgrove>
  * Diana Whitten <hurgleburgler>
  * Rodrigo Caballero <rcaballeromx>
  * Pieter Kruithof <piet>
  * Rob Cresswell <robcresswell>

Work Items
----------

#. Go through http://docs.openstack.org/contributor-guide/ui-text-guidelines.html
   with SME’s and determine what is outdated information.
#. Go through https://etherpad.openstack.org/p/mitaka-openstackux-heuristic and determine
   if this information is still relevant/wanted (this was the original plan for
   the UI guidelines, but has been scrapped by the team).
#. Ensure other project leaders are involved to collaborate on review pieces.
#. Determine gaps, and create new patterns where necessary.
        * What patterns already exist in each project? What overlaps?
        * What obvious gaps are in each project? Are there overlaps?


Dependencies
============

* This project is entirely dependent on full collaboration from each GUI
  project to ensure the aims and goals are met.

Testing
=======

Testing will follow the standard documentation review process.

References
==========

* Discussion can occur using any official medium including IRC in
  #openstack-doc, the openstack-docs mailing list with
  [ui-guidelines] in the subject.

  .. _`documentation team meeting`:
     https://wiki.openstack.org/wiki/Meetings/DocTeamMeeting
