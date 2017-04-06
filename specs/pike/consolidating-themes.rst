..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===========================================
Consolidating OpenStack themes across sites
===========================================


Problem description
===================

When a reader comes to a page on docs.openstack.org, they may see one of two
themes styling the page: either oslosphinxtheme or openstackdocstheme. By
having two themes for a single subdomain, we do not provide a consistent
experience for visitors to the site. The navigation provided on the top and
side of each page varies with these two themes, and now that there is a new
logo for OpenStack itself, we would like to consolidate both themes into one
theme, openstackdocstheme.

Also, from a maintenance standpoint, by continuing to support two themes, we
must maintain and provide bug fixes for two Sphinx themes with limited web
development resources.

Proposed change
===============

Here's an overview of all the tasks needed to use a single theme consistently
across all documents built to docs.openstack.org.

Theme work:

Update openstackdocs theme to match the logo used on www.openstack.org.

User interface changes that must be provided in openstackdocstheme that do not
exist currently:

* Provide the version number of the built documentation in the footer of the
  output. For example, "tempest 15.0.1.dev359 documentation" appears on each
  page of the Tempest documentation. Currently, openstackdocstheme provides the
  built date only, not the build version number.

* New logo that matches current logo used on www.openstack.org.

User interface differences that will not be ported from oslosphinx to
openstackdocstheme:

* Quick search form in bottom of left-hand navigation bar.

* Previous topic and Next topic shown in left-hand navigation bar.

* Return to project home page link in left-hand navigation bar.

* Customized list of links in header. For example, the page at
  https://docs.openstack.org/infra/system-config/ contains a custom header.

* When a landing page like https://docs.openstack.org/infra/ uses oslosphinx,
  the page should be redesigned with the new theme.

Configuration work:

Have all projects that build to the docs.openstack.org subdomain use the
openstackdocstheme theme instead of oslosphinx theme. Basically, update all
``conf.py`` files for documentation pages to use openstackdocstheme.

Make sure that the bug configuration is correct so that when a reader clicks
the "Log a bug" link in the built docs, the corresponding project's bug logging
location is opened.

Deprecate maintenance and use of the oslosphinx theme, addressing any unique
needs met by that theme within the openstackdocstheme.

Maintenance or project work:

Move any bugs in the backlog for oslosphinx theme to the openstack-doc-tools
bug queue at https://bugs.launchpad.net/openstack-doc-tools.

Alternatives
------------

Continue to use and maintain two themes, one for contributor documentation and
one for consumer documentation.

Alter oslosphinx theme to style all content like openstackdocstheme, basically
doing the opposite usage of themes proposed above. We could consider this
approach if it turns out that more ``conf.py`` files use the oslosphinx theme.

Implementation
==============

Assignee(s)
-----------


Work Items
----------

Communicate this spec to project teams.

Identify an Oslo liaison to help with any dependencies on reviews.

Ensure that the list of "lost" interface items is acceptable and that the list
itself is complete. If not, this spec and list should be modified.

Theme work listed above.

Configuration work listed above.

Maintenance work listed above.

Dependencies
============

Ensure other Oslo libraries do not have dependencies on the theme.

Testing
=======

Test that translations continue to work when using the openstackdocstheme for
all different types of content.

References
==========

https://bugs.launchpad.net/openstack-doc-tools
https://bugs.launchpad.net/oslo?field.searchtext=oslosphinx
http://lists.openstack.org/pipermail/openstack-docs/2017-April/009893.html
http://lists.openstack.org/pipermail/openstack-docs/2017-February/009752.html
