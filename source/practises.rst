.. _practises:

==========
Practices
==========

This section details the software development practices that we embrace and follow.

------------------------
Test Driven Development
------------------------

.. _tdd:

All code developed must follow the principles of Test Driven Development.
Developers must write tests before they begin work on any program.

TDD is a programming methodology where a programmer **first writes the test**
for a feature **before he writes the feature**.

TDD relies on repetition of the development cycle. Every single requirement
from the customer is translated into a test case, and then the software is
*improved* to pass these test cases. Doing so prevents the addition of new
code that breaks an old feature.

Breaking requirements/features into test-cases defines the problem in easy to
visualize portions, and they can be broken down into smaller portions for
The need for test-driven development is two-fold. One, it allows requirements
to be captured in very specific details. It allows developers to better
estimate how much time such requirements need. It also allows developers
to be able to estimate progress. Two, TDD ensures that future releases will
not break existing test cases.

The extensive test coverage this provides over time enables a project's state
to be constantly monitored, for its production readiness.

.. figure:: /_static/practises/tdd_outline_1.png
    :height: 500
    :align: center

    *Test-Driven Development for a Simple Program*

Test-driven development also encourages agile development. Code can be
released frequently, and with confidence that it does not break the dependency
chain. Furthermore, it enables management of configurations and addition of
new features or use cases with relative ease.


.. figure:: /_static/practises/tdd_outline_2.png
    :height: 500
    :align: center

    *Test-Driven Development to update an existing program with new feature.*


------
Scrum
------

As stated in the above section, every programming task must be broken into
tiny *features* that can be tested. This way, the development
and deployment can be measured and maintained with precision.


.. admonition:: Online Reference
    :class: tip

    If you are new to scrum, the official
    `Scrum webpage <https://www.scrum.org/resources/what-is-scrum>`_
    provides detailed guidelines on what Scrum is and how to implement it.

The core idea behind implementing scrum is to break apart complex tasks into
easy-to-measure features. This will ensure that the developer can generate
a mental roadmap of their work and managers can estimate the timeline.

-------------------
Code Readability
-------------------

Code must always be **readable**, both by the author and by other developers.
This is important because readable code can be easily debugged, understood by
one's peers and improved upon. A coding standard will be defined, but it is
necessary that developers still retain a little leeway when it comes to their
coding style. However, overall readability is paramount.

.. admonition:: Python Specific
    :class: tip
    
    To talk specifics for Python, it is recommended that the developer
    follows the guidelines described in
    `PEP 8 - Style Guide for Python Code <https://www.python.org/dev/peps/pep-0008/>`_.

------------------------
Constant Documentation
------------------------

Irrespective of the project and its scope, **all** code must be documented
constantly using internal docstrings or comments, and :doc:`Sphinx <sphinx:index>`
based documentation, using :term:`RST` or Markdown files. Documentation can be
compiled, if necessary, into MS Word or Powerpoint, but in no curcumstance
should they be originally written in that format. 

Documentation must be written so that it can be auto-rendered in various
formats, including, but not limited to: html, chm, latex, PDF, epub and kindle.


.. note::
    As an example of Sphinx's capabilities, this very document was generated
    using Sphinx, with a build script running on Jenkins.

###########################
Documentation Readability
###########################

Care must be taken so that documentation is **readable.** Long-winded
descriptions should be avoided, and diagrams should be used instead.
`Draw.io <https://draw.io>`_ is a fantastic tool for making diagrams.
In this particular team, this installation of
`draw.io <http://cae.driveline.gkn.com/draw.io/>`_ is safe and ready for usage.

Documentation must be written in English, and care should be taken to ensure
that it is comprehensible and provides extensive coverage of the code and how
to use the code.

.. note::

    `This post <http://divio.com/blog/documentation>`_ provides a great
    overview on documentation in general. Alternately, readers can watch 
    `this PyCon video <https://www.youtube.com/watch?v=azf6yzuJt54>`_ to
    watch the author describe his thoughts on the matter.

The project documentation should not be clubbed into one bucket. Instead,
care should be taken to ensure that the documentation is divided into easily
consumable formats, in four segments, so to speak. Doing so ensures that the
reader knows what documentation he or she is perusing, and the end result of
the documentation is easily defined as well. Where possible, verbose
descriptions of programming choices, and explicit assumptions regarding the
business logic must be defined. This ensures that future readers can
understand why certain judgements were made.

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
