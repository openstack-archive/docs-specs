..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

==========================================
Color support for osbash
==========================================

https://blueprints.launchpad.net/openstack-training-guides/+spec/osbash-color-support

Color variation to highlight messages and enhance readability while running
osbash scripts. Make this color variation compatible on most operating
systems - linux, windows, OSx.

Advantages:

* Enhances Readability
* Easier to debug
* Better understanding of sequence of events while running the scripts
* Adds color code to different types of messages eg. error, warning messages
* Adds to the asthetics when running scripts

Problem description
===================

A detailed description of the problem:

* Current scripts are mono-colored and do not provide sufficient readability
* Assigning different colors for different types of messages will
    * improve readability while running scripts
    * highlights the problems
    * easier debugging
    * help track the sequence of events
* Assigning background color to console while script execution will
    * provide uniform appearance across all consoles
    * uniform color contrast
* Support will be provided for all operating systems that run osbash (linux,
  windows, OSx)
* Target audience will be deployers

Proposed change
===============
* Implementing a colorizer for osbash scripts
* Making it compatible across linux, windows and OSx
* Having an option to change background color

Alternatives
------------
Running the existing scripts which have a mono-colored output

Disadvantages:

* Does not highlight different types of messages which help make the running
  scripts more readable and easier to debug
* Difficult to follow the sequence of events while the script runs

Implementation
==============

Assignee(s)
-----------

Primary assignee:
  sayalilunkad

Other contributors:
  None

Work Items
----------

* Devise color code for different type of messages and background
* Color code for background to be made optional
* Implement colorizer to assign these colors
* Make compatible across linux, windows and OSx

Dependencies
============
None

Testing
=======
Run the scripts to check if the colorizer assigns the designated colors to
the output of the script.

References
==========
None
