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


-------------------
Code Readability
-------------------

Code must always be **readable**, both by the author and by other developers. This is important because readable code can be easily debugged, understood by
one's peers and improved upon. A coding standard will be defined, but it is necessary that developers still retain a little leeway when it comes to their coding
style. However, overall readability is paramount.

.. note::

    To talk specifics for Python, it is recommended that the developer follows the guidelines described in
    `PEP 8 - Style Guide for Python Code <https://www.python.org/dev/peps/pep-0008/>`_.


------------------------
Constant Documentation
------------------------

Irrespective of the project, all code must be documented constantly using internal docstrings or comments, and Sphinx-documentation, either in the
form of :term:`RST` or Markdown files. Documentation can be compiled, if necessary, into MS Word or Powerpoint, but in no curcumstance should they be originally
written in that format. The reason for this choice is because sphinx-based documentation is easy to version control and build in different formats.
All the logos, images and directives can be easily updated on demand with a simple change. Company logos evolve and the palettes change.
Documentation should be written so that it can be rendered in various formats, including, but not limited to: html, chm, latex, PDF, epub and kindle.

.. only:: latex

    This PDF was compiled using Sphinx and miktex.

.. only:: epub

    This Epub was compiled using Sphinx.

Tools such as gitlab and jenkins make it trivial to automatically build documentations on commit. Additionally, Gitlab and Github can render documention natively as long as it is pushed to a separate branch. This makes it easy to host documentation alongside the source code, and eliminates the need for separate hosting for docs altogether.

###########################
Documentation Readability
###########################

Care must be taken so that documentation in readable. Long-winded descriptions should be avoided, and diagrams should be used instead. `Draw.io <https://draw.io>`_ is a fantastic tool for making diagrams. It can also be deployed locally on premises without much trouble.

Documentation should be written in English, and care should be taken to ensure that it is comprehensible and provides extensive coverage of the code and how to use the code.

.. note::

    `This post <http://divio.com/blog/documentation>`_ provides a great overview on documentation in general. Alternately, readers can watch `this PyCon video <https://www.youtube.com/watch?v=azf6yzuJt54>`_ to watch the author describe his thoughts on the matter.

The project documentation should not be clubbed into one bucket. Instead, care should be taken to ensure that the documentation is divided into easily consumable formats, in four segments, so to speak.
Doing so ensures that the reader knows what documentation he or she is perusing, and the end result of the documentation is easily defined as well. Where possible, verbose descriptions of programming
choices, and explicit assumptions regarding the business logic must be defined. This ensures that future readers can understand why certain judgements were made.

+-----------------------------------------------------+-----------------------------------------------------------+
| **TUTORIALS**                                       | **HOW-TO GUIDES**                                         |
|                                                     |                                                           |
| A tutorial:                                         | A how-to guide:                                           |
|                                                     |                                                           |
| is learning-oriented                                | is goal-oriented                                          |
|                                                     |                                                           |
| allows the newcomer to get started                  | shows how to solve a specific problem                     |
|                                                     |                                                           |
| is a lesson                                         | is a series of steps                                      |
|                                                     |                                                           |
| Analogy: teaching a small child how to cook         | Analogy: a recipe in a cookery book                       |
+-----------------------------------------------------+-----------------------------------------------------------+
| **EXPLANATION**                                     | **REFERENCE**                                             |
|                                                     |                                                           |
| An explanation:                                     | A reference guide:                                        |
|                                                     |                                                           |
| is understanding-oriented                           | is information-oriented                                   |
|                                                     |                                                           |
| explains                                            | describes the machinery                                   |
|                                                     |                                                           |
| provides background and context                     | is accurate and complete                                  |
|                                                     |                                                           |
| Analogy: an article on culinary social history      | Analogy: a reference encyclopaedia article                |
+-----------------------------------------------------+-----------------------------------------------------------+

*Table: Dividing documentation into four easy to understand types*

.. note::

    For the interested, this document is a reference document.


