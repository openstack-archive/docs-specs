..
 This work is licensed under a Creative Commons Attribution 3.0 Unported
 License.

 http://creativecommons.org/licenses/by/3.0/legalcode

===========================================
Hands-on assessment for the Training Guides
===========================================



https://blueprints.launchpad.net/openstack-training-guides/+spec/hands-on-assessments

Trainees need to assess their knowledge in a real life scenario after each phase of the Training guides programs (hands-on evaluation). This is different kind of assessment as is done in the online quizzes scenario. 


Problem description
===================

Trainees need to be tested in a scenario that is as close as possible to a real-life use case of OpenStack clouds.

Examples for the Associate guide:

* import a new image and start a new VM from it
* create a new volume and attach it to the running VM
* From the textual description of the fictitious organization create new tenants and new users, define suitable resource quotas, import images and define their visibility
* etc.

Proposed change
===============

We need to define a list of suitable scenarios and define a procedure for their execution during/after training sessions. We should also provide an easy to use solution checklist that trainers can use to assess a correctness. If online platform will be used, automatic assessment is preferred.

Alternatives
------------

No hands-on assessment. This could be verified in an OpenStack certification program. It could be OpenStack Foundation approved certification program or even vendor approved certification program, if they adopt Training Guides as a base material which they extend.

Implementation
==============

Assignee(s)
-----------

Primary assignee:

matjazp

Work Items
----------

* Identify suitable real-life use case scenarios (high level)
* Define a detailed step-by-step procedure that trainees must implement
* Explore options for hosting of the testing cluster or testing VMs
* Explore options for grading of the finished assessments
* Explore options for providing feedback and statistics

Dependencies
============

Should be done with BP https://blueprints.launchpad.net/openstack-training-guides/+spec/online-quizzes
 in mind, so there's no overlap in content of the assessments. Or, alternatively, we could take questions from online quizzes and weave them together into a suitable scenario.


Testing
=======

Collect feedback from the trainers. 

References
==========

None
