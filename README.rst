======================================
OpenStack Documentation Specifications
======================================

This git repository is used to hold approved design specifications for additions
to the OpenStack Documentation program. Reviews of the specs are done in gerrit, using a
similar workflow to how we review and merge changes to the docs and supporting tools.

The layout of this repository is::

  specs/<release>/

You can find an example spec in `doc/source/specs/template.rst`. 
Fill it in with the details of a new blueprint for documentation.

For docs, blueprints are required for larger, coordinated projects but not for small
fixes. It's a judgement call for whether you need a spec, so feel free to ask in the
#openstack-doc IRC channel or on the openstack-docs mailing list.

To propose a specification for a release-specific doc like the install guides
or the configuration reference, add a new file to the
`specs/<release>` directory and post it for review.  The implementation
status of a blueprint for a given release can be found by looking at the
blueprint in Launchpad (and the spec links to Launchpad). 

Please realize that not all approved blueprints will get fully implemented.

Prior to the Juno development cycle, this repository was not used for spec
reviews.  Reviews prior to Juno were completed entirely through Launchpad
blueprints::

  http://blueprints.launchpad.net/openstack-manuals

Please note, Launchpad blueprints are still used for tracking the
current status of blueprints. For more information, see::

  https://wiki.openstack.org/wiki/Blueprints

For more information about working with gerrit, see::

  https://wiki.openstack.org/wiki/Gerrit_Workflow

To validate that the specification is syntactically correct (i.e. get more
confidence in the Jenkins result), please execute the following command::

  $ tox

After running ``tox``, the documentation will be available for viewing in HTML
format in the ``doc/build/`` directory. Please do not check in the generated
HTML files as a part of your commit.

The files are published at::

  http://specs.openstack.org/openstack/docs-specs

Repository location is::

  http://git.openstack.org/cgit/openstack/docs-specs/
