===============================
Software Development Process
===============================

.. todo::

    Explain how different tasks are tackled some have long term viewpoints,
    others have short term usage cycles. All of them should have tests.


The following diagram provides a bird's-eye-view of the software development
process that must be followed here.

.. _fig_soft_dev:

.. figure:: /_static/process/software_development_process.png
    :width: 600

    A Bird's Eye View of Software Development Process

The following sections of this chapter describe how developers carry out each
stage of this process.

---------------------------------------
Requirements Gathering
---------------------------------------

When a new request for a program is created, the developer must approach the
customer to understand their requirements completely. At this stage, no code
is actually written. Instead, the developer must record a series of questions
to ask the customer so as to understand the exact requirements.

:ref:`The Requirements Gathering Template <appendix_a>` provides a
sample set of questions developers can ask to capture this information

This step **must** be carried out as detailed as possible, so that the
developer can understand the requirements of the task at hand. It is then
the duty of the developer to convert these requirements into a task
definition.

.. _taskdef::

---------------------------------------
Task Definition
---------------------------------------

After gathering the requirements, the developer must convert the requirements
into a task definition, breaking up the task into *features*. These features
are to be as detailed as possible, providing timelines and infrastructure
guidelines for each.

:ref:`The Task Definition Template <appendix_b>` provides a set of questions
a developer to look into so as to capture this information.

This step is conducted in order to convert the requirements into a more
verbose description of the task at hand. At this stage, the customer might
be contacted to gather details regarding the types of users, the volume,
permissions to gather usage metrics and runtime errors automatically,
and other details that can help the developer and the customer agree on the
task, the timeline and the deliverables.

This definition must target two different people: the developer, and the
customer.

The customer's portion of this definition must define the details which are
relevant to the customer. This must cover the billing accounts, the agreed
timeline, the maintenance scope and the end results/features.

The developer's portion of this definition must define, in great detail, the
features, the stack that is chosen for this task and the justification (in
minimal detail, if previously justified in a similar task) for said stack
choices, as well as the system design diagram. The developer must also prepare
adequate interaction diagrams which showcase how a system interacts with
different components, be it in UML format or a flow chart.

This stage should be considered complete when both parties sign off on the
task having understood what will be the end result and when it will be
delivered.

---------------------------------------
Development Templates
---------------------------------------

Once the requirements are gathered and the task defined, the developer must
then select the appropriate template for this program. If the template does
not exist, it will have to be created. Time for this step must be accounted
for in the task definition stage.

Once the template is ready, it will have to be used to generate the program
folder and file structure. This will have to be initially committed into the
appropriate project repository.

If the program is a project-agnostic one, such as a general library or
microservice, it will have to be added to the software development
project repository.

If the program is project-specific and has business-logic coded into it, it
will have to be added to the appropriate project or way of working (WoW).

------------------------
Test-Driven Development
------------------------

Prior to the start of the task, the developer must write tests for the core
functionality of this program. For a microservice, the endpoints will have
to be tested. For a CLI, all options and parameters must be tested.
For an interface, both the backend and frontend must be tested.

Once failing tests are written, the code will have to be updated so that the
tests eventually pass. This cycle is repeated until all the features outlined
in the requirements and task definition sections are answered.

.. note::

    See the :ref:`Test Driven Development <tdd>` section for more details
    regarding the practise and how we follow it at GKN.

.. _fig_deployment:

.. figure:: /_static/process/deployment.png
    :width: 600
    :alt: Deployment Process Diagram

    *Deployment Process Diagram*

------------------------
Deployment
------------------------

During the development of the program, the developer must also put in thought
to the deployment of said code. The following diagram illustrates
the deployment methodology for different kinds of programming tasks.

:numref:`Figure %s <fig_deployment>` illustrates how different types of
applications are deployed.

In summary:

1. Jenkins to build wheels, docker images and distributables.
2. Docker Registry to history.
3. Apache Mesos to launch services across machines.

However, the developer may also encounter tasks with unique deployment
methodologies, such as installation via remote-desktop protocol or something
similar.

These deployments will have to be treated in an appropriate way, but it is
the duty of the developer to investigate if the deployment *can* indeed be
automated.

------------------------
Support
------------------------

.. _fig_support:

.. figure:: /_static/process/support.png
    :width: 400
    :alt: Software Support

    *Software Support Scope*

All tasks should be divided into three categories:

1. Continuous Development
2. Maintenance
3. One-Off Products

:numref:`Figure %s <fig_support>` provides a rudimentary way to demarcate
projects into support scope based on their definition.

All programs developed by the team must be assessed for maintenance scope,
as indicated in the :ref:`Task Definition Section <taskdef>` above.
This helps the customer understand how the product will be supported in the
future.

Bugs must be tracked through the ticketing system, which, for the foreseeable
future is Redmine.

.. admonition:: Future Prospects
    :class: note

    In the future, Gitlab-CE will be the *de-facto* system for CI/CD, SCM and
    bug tracking for **all** software products here at GKN Driveline. This
    process is not initiated, however it will be conducted once the team has
    at least 3-4 members.

Continuous Development
------------------------

All software that is developed for a large-scale deployment is automatically
classified under *Continuous Development*. The support that is provided for
such products include:

1. Continuous Development
2. Prompt Bugfixes
3. Prioritization of New Features

.. warning::

    Continuous Development does **not** have anything to do with the
    **CD** acronym in **CI/CD**. This document will describe that later.

    However, it should suffice to the layman to understand that in the current
    context, both are similar. **Only** in our context.

Maintenance
--------------

All software that is meant to be used at least periodically should have some
maintenance scope defined for it.

This scope is defined in two ways:

Short-Term Maintainance
*************************

Such products are maintained only for a short period of time. This depends on
the initial agreement, but should not exceed *one month* after the last stable
release.

Long-Term Maintenance
***********************

Some products demand a higher level of maintenance. These can be maintained
for *six-months* to *a year* depending upon the priority. However, any product
that is defined under this plan should have a scope to be moved into the
*Continuous Development* Stage unless the scope vanishes at the end of the
aforementioned timeframe.

One-Off Products
---------------------

All software that is deployed or written for one-off use-cases, or niche cases
which have no future prospects, is considered to be **One-Off** and no
maintenance scope is defined for them past the first stable release.

These scripts should be only considered if there is an extreme time component
that can be saved by automating them, however it is to be recognized that the
script will not be maintained or improved unless there is an urgent business
case.
