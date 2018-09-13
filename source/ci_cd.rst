.. ci_cd:

=======================================
Deploying Code to Production : CI / CD
=======================================

This section defines a few methodologies of development and deployment that are being followed in the industry. At the outset,
it seems appropriate that we follow a **Continuous Deployment** model. Of course, this stands to change with time and adequate debate.

CI and CD are popular acronyms in use in modern development lifecycles. CI stands for Continuous Integration, a practise that seeks
to simplify the steps towards a release. CD, however, is twofold in meaning.

.. image:: /_static/testing/deployment.png
    :height: 350
    :align: center

.. _ci:

------------------------
Continuous Integration
------------------------

In a continuous integration system, developers write their code in branches, isolating features. However, the system seeks to merge
these changes back into a common development branch so that they can collaborate easier. Doing so avoids what is known as "Integration Hell",
a problem that arrives when developers wait too long to integrate their changes into the root branch of the repository.

A CI tool such as Gitlab CI is pivotal for integrating branches together with ease.

----------------------
Continuous Delivery
----------------------

Continuous Delivery is an extension to the CI model, making sure that all changes can be delivered to the customer quickly. This depends on robust
automated testing, wide test coverage and an automated release process. By embracing Continuous Delivery, the team seeks to simplify its deployment
process, perhaps at a click of a button. However, the deployment itself is not automated. It must be triggered by a lead developer or source code manager.

This allows a short timeframe of forthnightly or weekly releases.

----------------------
Continuous Deployment
----------------------

Continuous Deployment is an extension atop Continuous Delivery, seeking to automate the deployment stage as well. This practice ensures that all
changes to the production branch are released to the customers, after running and passing all automated tests, of course. There is no human factor
in the deployment process, and this process assumes that the end user is also a tester. It is a simple process that makes rapid development and
continuous improvement possible. This frees the development team from a "release date", and it gives the developers freedom to see their work
go live in moments.


.. image:: /_static/testing/ci_cd.png
    :align: center
    :height: 300

*Illustration: Continuous Integration, Delivery and Deployment*


-----------------
CI / CD Tools
-----------------

Using modern tools such as :term:`Jenkins` or :term:`GitLab` for CI/CD tasks enables developers to focus on the code and leave the integration,
delivery and deployment to a system that takes care of it all.

All developers would have to do is organize their project in a standard way that can be configured. For example:

::

    project
    ├── AUTHORS.rst
    ├── docs
    ├── Dockerfile
    ├── demo.py
    ├── HISTORY.rst
    ├── CONTRIBUTING.rst
    ├── LICENSE.md
    ├── module
    │   ├── __init__.py
    │   └── package.py
    ├── project.cfg
    ├── requirements.txt
    ├── README.rst
    ├── server.py
    ├── setup.py
    ├── static
    ├── templates
    ├── MANIFEST.in
    ├── Makefile
    └── tests
    └── tox.ini

In such a folder structure, relevant to python projects, a CI/CD tool is able to understand that the ``tests`` directory contains all relevant tests.
The ``Dockerfile`` contains instructions related to building the service and running it. These are standardized, and we should make the best use of them.

Needless to say, these can be further customized and used.


------------------------------------------
Enabling Long Term Maintenance & Support
------------------------------------------

CI/CD pipelines allow **continuous** support and delivery. The moment something goes wrong in the pipeline, the developers will know it before the users do.
This methodology helps keep an atmosphere of calm and constant availability of production-grade systems.

Furthermore, with tools such as :term:`Gitlab` or :term:`Github`, the code repositories are available for all concerned parties to see, and raise tickets.
Users of the software can easily raise concerns related to features or possible bugs on the source code repositories, and developers can put it on their todo list.

Even if a developer leaves a project, his work is available for all those concerned, and the practises outlined earlier ensure that his work is clearly documented,
tested and other developers can continue his work.
