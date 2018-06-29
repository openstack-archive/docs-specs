..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==================================================
Front page template for project team documentation
==================================================

Use consistent content structure on the front page across all OpenStack
project team documentation hosted on docs.openstack.org.

Problem description
===================

Actionable feedback gathered at the `Queens PTG docs project meeting`_
included requests for the Documentation Project to provide guidance and a set
of recommendations on how to structure common content typically found on the
front page for project team docs, located at ``doc/source/index.rst`` in the
project team repository.

The goal of this change is to make it easier for users to find, navigate, and
consume project team documentation, and for contributors to set up and
maintain the project team documentation.

The recommended template as described in this spec would be included in the
`OpenStack Documentation Contributor Guide`_ as part of the project team setup
docs. The `Cookiecutter Template for new OpenStack projects`_ would also be
updated for changes described in this spec.

The recommendations for the project team front page would serve as the basis
for one of the future governance docs tags. Project teams would use the future
docs tag to show the maturity of their documentation and adherence to
community recommendations.

The definition of governance docs tags would be covered in a separate spec.

Proposed change
===============

The main idea behind the recommended content structure is to outline the
content based on target audience groups. The main audience groups are defined
as end users, operators, and contributors.

This template reuses some ideas from the front page of the `OpenStack Compute
service`_. Projects are encouraged to make additional changes to the template
per their specific needs so long as the design and structure ideas are
retained.

.. code-block:: rst

   =======================================================
   OpenStack {{service name}} ({{codename}}) documentation
   =======================================================

   What is {{codename}}?
   ~~~~~~~~~~~~~~~~~~~~~

   {{codename}} is the OpenStack {{service name}} service that...

   For end users
   ~~~~~~~~~~~~~

   As an end user of {{codename}}, you want to... so that...

   Using {{codename}}
   ------------------

   Contents:

   .. toctree::
      :maxdepth: 1

      user/index

   Using the {{codename}} API
   --------------------------

   Resources:

   * `{{codename}} API <http://developer.openstack.org/api-ref/{{codename}}/>`_

   For operators
   ~~~~~~~~~~~~~

   As an operator of {{codename}}, you want to... so that...

   Installing {{codename}}
   -----------------------

   Contents:

   .. toctree::
      :maxdepth: 1

      install/index

   Administrating {{codename}}
   ---------------------------

   Contents:

   .. toctree::
      :maxdepth: 1

      admin/index

   Reference
   ---------

   Contents:

   .. toctree::
      :maxdepth: 1

      configuration/index
      cli/index

   Additional resources
   --------------------

   * `{{codename}} release notes <https://docs.openstack.org/releasenotes/{{codename}}/>`_

   For contributors
   ~~~~~~~~~~~~~~~~

   As a contributor to {{codename}}, get started with... Learn more about...

   Contributing to {{codename}}
   ----------------------------

   Contents:

   .. toctree::
      :maxdepth: 1

      contributor/index

   Additional reference
   --------------------

   Contents:

   .. toctree::
      :maxdepth: 1

      reference/index

   Indices and tables
   ~~~~~~~~~~~~~~~~~~

   * :ref:`genindex`
   * :ref:`modindex`
   * :ref:`search`

Alternatives
------------

#. Do nothing.

   Essentially, maintain the status quo by not providing any guidance on
   structuring content on the front page besides the ``doc/`` directory
   structure as defined in `Project guide setup`_ in the OpenStack
   Documentation Contributor Guide.

   The status quo makes it more difficult for users to find, navigate, and
   consume project team documentation, and for contributors to set up and
   maintain the project team documentation.

#. Structure the front page based on current high-level groupings.

   Consistently organize the content on front pages based on subdirectories in
   the ``doc/`` directory of each project team repository, such as
   ``install/``, ``contributor/``, or ``configuration/``.

   This might make it difficult for users to navigate the front page if there
   are too many documents linked from that page.

Implementation
==============

Assignee(s)
-----------

* Petr Kovar (pkovar)
* Documentation team PTL for Stein
* Documentation team
* Project teams

Work items
----------

* Update the OpenStack Documentation Contributor Guide with the template.
* Update the Cookiecutter Template for new OpenStack projects with the
  template.
* Project teams provide patches for their project team documentation to
  implement the changes to the front page.

Dependencies
============

Get a buy-in and commitment from project teams and the OpenStack community
to actively implement the changes to project team documentation.

Testing
=======

Testing would follow the standard review process as defined by project teams.

References
==========

* `Project guide setup`_
* `Cookiecutter Template for new OpenStack projects`_
* `OpenStack Documentation Contributor Guide`_
* `Queens PTG docs project meeting`_
* :doc:`../pike/os-manuals-migration`
* `OpenStack Compute service`_

.. _Project guide setup: https://docs.openstack.org/doc-contrib-guide/project-guides.html
.. _Cookiecutter Template for new OpenStack projects: https://git.openstack.org/cgit/openstack-dev/cookiecutter/
.. _OpenStack Documentation Contributor Guide: https://docs.openstack.org/doc-contrib-guide/
.. _Queens PTG docs project meeting: https://etherpad.openstack.org/p/docs-i18n-ptg-rocky
.. _OpenStack Compute service: https://docs.openstack.org/nova/latest/
