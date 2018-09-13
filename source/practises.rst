.. _practises:

==========
Practices
==========

This section details the software development practices that we embrace and follow.

.. _tdd:

------------------------
Test-Driven Development
------------------------

TDD is a programming methodology where a programmer **first writes the test** for a feature **before he writes the feature**.

TDD relies on repetition of the development cycle. Every single requirement from the customer is translated into 
a test case, and then the software is *improved* to pass these test cases. Doing so prevents the addition of new code
that breaks an old feature.

Breaking requirements/features into test-cases defines the problem in easy to visualize portions, and they can be broken down into
smaller portions for 
The need for test-driven development is two-fold. One, it allows requirements to be captured in very specific details. It allows developers
to better gauge how much time such requirements need. It also allows developers to be able to gauge progress. Two, TDD ensures that future
releases will not break existing test cases. 

The extensive test coverage this provides over time enables a project's state to be constantly monitored, for its production readiness.

.. image:: /_static/practises/tdd_outline_1.png
    :height: 500
    :align: center

*Illustration: Test-Driven Development for a Simple Program*

Test-driven development also encourages agile development. Code can be released frequently, and with confidence that it does not break
the dependency chain. Furthermore, it enables management of configurations and addition of new features or use cases with relative ease.


.. image:: /_static/practises/tdd_outline_2.png
    :height: 500
    :align: center

*Illustration: Test-Driven Development to update an existing program with new feature.*


------
Scrum
------

As stated in the above section, every programming task should be broken into tiny usecases that can be tested. This way, the development
and deployment can be measured and maintained with precision. 


.. admonition:: Online Reference
    :class: tip

    This section is largely adapted from `the official Scrum webpage <https://www.scrum.org/resources/what-is-scrum>`_. Reading that page directly is recommended.


**Scrum** is a software development *philosophy* that originates from **Agile Software Development** principles.
involves simple practises. Coding tasks should be broken into small portions, their timeframe should be measurable and they should be captured in
a way that is easy to visualize, such as a **Kanban** board. This board can be a project management tracker, which tracks states of projects,
or a simple board on which someone marks the status of the project.

**Scrum** is **simple**. It defines three roles, the Product Owner, Scrum Master and Development Team Member. All roles fall under one of these three roles.
Following **Scrum** principles involves **events** and **artifacts.**

##############
Scrum Events
##############

Prescribed events are used in Scrum to create regularity and to minimize the need for meetings not defined in Scrum. All events are time-boxed. Once a Sprint begins, its duration is fixed and cannot be shortened or lengthened. The remaining events may end whenever the purpose of the event is achieved, ensuring an appropriate amount of time is spent without allowing waste in the process.  The Scrum Events are:

* Sprint
* Sprint Planning
* Daily Scrum
* Sprint Review
* Sprint Retrospective

#################
Scrum Artifacts
#################

Scrum’s artifacts represent work or value to provide transparency and opportunities for inspection and adaptation. Artifacts defined by Scrum are
specifically designed to maximize transparency of key information so that everybody has the same understanding of the artifact. The Scrum Artifacts are:

* Product Backlog
* Sprint Backlog
* Increment
