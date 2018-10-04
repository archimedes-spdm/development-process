===============================
Software Development Process
===============================

.. todo::

    Explain how different tasks are tackled some have long term viewpoints,
    others have short term usage cycles. All of them should have tests.


The following diagram provides a bird's-eye-view of the software development process that must be followed here.

.. _fig_soft_dev:

.. figure:: /_static/process/software_development_process.png
    :width: 600
    :align: center

    A Bird's Eye View of Software Development Process

The following sections of this chapter describe how developers carry out each stage of this process.

---------------------------------------
Requirements Gathering
---------------------------------------

Once a customer approaches a developer for a task, the following questions must be answered.

1. Is this a new program?
2. Is this a new feature into an existing program?

Depending upon these questions, the developer must ask the customer as much detail as possible about the task at hand.
This must include, but not be limited to, the following:

1. How often will this solution be used?
#. What sort of end result is the customer expecting?
#. Is it an improvement to an existing process?
#. Does the program require a graphical user interface?
#. Does the program have user judgement involved, or can it be completely automated given a bunch of initial input?
#. Does the program deal with proprietary formats that can only be read with third-party software?
#. Does the program deal with data formats of over 1 GB in size?
#. Does the program deal with data formats of over 100 GB in size?
#. Does the program deal with data formats of over 1 TB in size?
#. How long does the current process take?
#. Does the program deal with non-standard engineering formulae?
#. Does the program deal with unique input data formats, which are non-standard, such as an MS Excel spreadsheet with some specific schema?
#. Can said schema be better designed, or is the schema inflexible?
#. Can the program directly use a file format that is output from another program?
#. Does the program deal with text-based file formats?

These questions, and any additional questions must be recorded in the task management system.
It is the responsibility of the developer to explain these questions to the customer and capture their exact requirements before
the task is defined.

.. note::

    These questions should be as exhaustive as possible, so as to capture the unique requirements comprehensively.
    These assist the judgement of the developer to assess what technology to use while starting the task.

.. _taskdef::

---------------------------------------
Task Definition
---------------------------------------

Given the answers to the above section, the developer must consult his or her experience and make a judgement about features.
They should get back to the customer and address the following:

1. What is the technology that will be used to develop this program?
#. Will this program require additional hardware or software that is new to our stack?
#. Will this program provide users an interface to use it?#. Will the program have a graphical user interface?#. Will the program have a command line interface?#. Will the program require the creation of a new parser library?#. Will the program require the creation of a microservice?#. Will the program require a new set of UI components to be developed for the web interface?#. Will the program be executed on the user's computer or on a server?
#. Will the program be mappable to an existing pipeline so that it can be triggered after a previous event?
#. Will the program have a long term support scope?
#. Will the program have a short term support scope?
#. Will the program have timed, frequent updated?
#. Will the program be a one-off script that has no scope of support in the foreseeable future?
#. How many man-hours will the program require for a prototype?
#. How many man-hours will the program require for a stable release?
#. What is the scope of data inputs that this program will support?
#. What is the minimum-user configuration that this program will require?
#. What is the level of permissions a user requires to execute this program?
#. Can this development be sped up by adding additional developers?
#. Can this program be completely automatable so that it runs on a trigger event?
#. Does this program require the creation of a new cookiecutter template?

These questions, and any additional questions must be recorded in the task management system. The developer can use these questions
to begin work on the task after the approval.

---------------------------------------
Development Templates
---------------------------------------

Once the requirements are gathered and the task defined, the developer must then select the appropriate ``cookiecutter`` template
for this program. If the cookiecutter template does not exist, it will have to be created.

Once the cookiecutter template is chosen, it will have to be used to generate the program folder and file structure.
This will have to be initially committed into the appropriate project repository.

If the program is a project-agnostic one, such as a general library or microservice, it will have to be added to the software development
project repository.

If the program is project-specific and has business-logic coded into it, it will have to be added to the appropriate project or WoW.

------------------------
Test-Driven Development
------------------------

Prior to the start of the task, the developer must write tests for the core functionality of this program.
For a microservice, the endpoints will have to be tested.
For a CLI, all options and parameters must be tested.
For an interface, both the backend and frontend must be tested.

Once failing tests are written, the code will have to be updated so that the tests eventually pass. This cycle is repeated until all the
features outlined in the requirements and task definition sections are answered.

.. note::

    See the :ref:`Test Driven Development <tdd>` section for more details regarding the practise and how we follow it at GKN.

.. _fig_deployment:

.. figure:: /_static/process/deployment.png
    :width: 600
    :figclass: align-center
    :align: center
    :alt: Deployment Process Diagram

    *Deployment Process Diagram*

------------------------
Deployment
------------------------

During the development of the program, the developer must also put in thought to the deployment of said code. The following diagram illustrates
the deployment methodology for different kinds of programming tasks.

:numref:`Figure %s <fig_deployment>` illustrates how different types of applications are deployed.

In summary:

1. Jenkins to build wheels, docker images and distributables.
2. Docker Registry to history.
3. Apache Mesos to launch services across machines.

------------------------
Support
------------------------

.. _fig_support:

.. figure:: /_static/process/support.png
    :align: center
    :width: 400
    :alt: Software Support

    *Software Support Scope*

All tasks should be divided into three categories:

1. Continuous Development
2. Maintenance
3. One-Off Products

:numref:`Figure %s <fig_support>` provides a rudimentary way to demarcate projects into support scope based on their definition.

All programs developed by the team must be assessed for maintenance scope, as indicated in the :ref:`Task Definition Section <taskdef>` above.
This helps the customer understand how the product will be supported in the future.

Bugs must be tracked through the ticketing system, which, for the foreseeable future is Redmine.

.. admonition:: Future Prospects
    :class: note

    In the future, Gitlab-CE will be the *de-facto* system for CI/CD, SCM and bug tracking for **all**
    software products here at GKN Driveline. This process is not initiated, however it will be conducted
    once the team has at least 3-4 members.

Continuous Development
------------------------

All software that is developed for a large-scale deployment is automatically classified
under *Continuous Development*. The support that is provided for such products include:

1. Continuous Deployment
2. Prompt Bugfixes
3. Prioritization of New Features

.. warning::

    Continuous Development does **not** have anything to do with the **CD** acronym in **CI/CD**. This document will describe that later.

Maintenance
--------------

All software that is meant to be used at least periodically should have some maintenance scope defined for
it.

This scope is defined in two ways:

Short-Term Maintainance
*************************

Such products are maintained only for a short period of time. This depends on the initial agreement, but should not exceed one month after the last stable release.

Long-Term Maintenance
*************************

Some products demand a higher level of maintenance. These can be maintained for six-months to a year depending upon the priority. However, any product that
is defined under this plan should have a scope to be moved into the Continuous Development Stage unless the scope vanishes at the end of the aforementioned
timeframe.

One-Off Products
---------------------

All software that is deployed or written for one-off use-cases, or niche cases which have
no future prospects, is considered to be **One-Off** and no maintenance scope is defined
for them.

These scripts should be only considered if there is an extreme time component that can
be saved by automating them, however it is to be recognized that the script will not
be maintained or improved unless there is an urgent business case.
