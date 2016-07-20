..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==============================================
Consistent file naming for search optimization
==============================================

Problem description
===================

Now that the migration to RST has settled down, we can see that using the
former xml:id for file names meant that some RST file names use underbar (_) as
space indicators and some RST file names use hyphen (-) as space indicators.

Our conventions are to use hyphens for all RST files so that the resulting
built HTML files are human-readable and search-engine-readable.

Proposed change
===============

Update all files in the openstack-manuals repository, a guide at a time, to
match our convention of using hyphens for RST file names.

Change any RST file names using underscore to use hyphen instead. Do not change
file names if they use hyphens for spacing.

Change any folder names using underscore if and only if the folder results in
output on a URL that contains an underscore.

Do not change image or figure file names.

Change any hyperlinks that refer to underscore-named files.

Redirect any old file names to new file names on the web server itself in the
``static/www/.htaccess`` file.

Alternatives
------------

Keep the file names as-is and change our convention to use either hyphens or
underscores. This results in decreased findability for files on the site.

Implementation
==============

Assignee(s)
-----------

admin-guide: Anne Gentle
cli-reference: Kato Tomoyuki
config-reference: Kato Tomoyuki
common: Akihiro Motoki
user-guide: Mariia Zlatkova

backporting link fixes: Akihiro Motoki

Needs an owner: ops-guide

Work Items
----------

Change file names and links in:

admin-guide
cli-reference (glance_property_keys.rst is the only file)
common
config-reference
ops-guide
user-guide

These guides have no need to change file names:

arch-design
config-reference
contributor-guide
ha-guide
image-guide
install-guide
install-guide-debconf

Change links in stable/mitaka and stable/liberty branches that go to changed file names
due to changes in non-versioned deliverables by backporting link changes.

Dependencies
============

Coordination of efforts and landing patches.

Testing
=======

Test changed file names for no broken links resulting.

Test redirects.

References
==========

Contributor guide: http://docs.openstack.org/contributor-guide/docs-structure.html#file-naming-conventions

To get the list of Work Items I ran this type of search::

    ls ~/src/openstack-manuals/doc/user-guide/source/ | grep _
