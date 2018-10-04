===================
Technology Stack
===================

This section of the documentation details the technologies that we use in production.

------------------------
Programming Languages
------------------------

***********
Python
***********

Python is the basic language of choice. For all areas where possible, the use of Python 3.7 (CPython) is encouraged.
The use of Python 2.7 is only advocated where absolutely necessary. All projects that utilize Python 2.7 must plan
for a migration to 3.7.

.. _py23:

Why Python 3
--------------

Python 3.7 is the default version of Python to be used for all new scripts,
programs and projects. To be even more specific, Python 3.7.0, *CPython* must
be used. Other versions of Python are to be avoided, unless there is a clear
business case.

.. warning::

    Do not mistake **CPython** for :doc:`Cython. <cython:index>` Cython may be used where speed is a
    necessity, however, alternate solutions such as CUDA or C are encouraged
    for this.

#################################
Python Project Folder Structure
#################################

All standard tasks have well defined folder structures which are to be replicated using
:doc:`cookiecutter <cookiecutter:index>` templates.
These templates can be found in the appropriate repository and can be deployed using the steps detailed in the
:doc:`cookiecutter documentation. <cookiecutter:index>`

Folder Structure for Microservices
====================================

This folder structure is defined by the cookiecutter project stored
`here <https://gitlab.driveline.gkn.com/cookiecutter-templates/microservices>`_.

::

    service
    ├── AUTHORS.rst
    ├── docs
    ├── Dockerfile
    ├── demo.py
    ├── HISTORY.rst
    ├── CONTRIBUTING.rst
    ├── LICENSE.md
    ├── service
    │   ├── __init__.py
    │   ├── swagger.yml
    │   ├── db.py
    │   ├── models.py
    │   ├── server.py
    │   └── package.py
    ├── project.cfg
    ├── requirements.txt
    ├── README.rst
    ├── run_service.py
    ├── setup.py
    ├── static
    ├── templates
    ├── MANIFEST.in
    ├── Makefile
    ├── tests
    └── tox.ini


Folder Structure for Command Line Tools
========================================

This folder structure is defined by the cookiecutter project stored
`here. <https://gitlab.driveline.gkn.com/cookiecutter-templates/cli>`_

.. note::

    For command line tools in python, use :term:`pipsi` instead of pip to
    enable the deployment of the cli. See this
    `readme <https://github.com/mitsuhiko/pipsi#readme>`_ to understand more.

::

    script
    ├── AUTHORS.rst
    ├── docs
    ├── HISTORY.rst
    ├── CONTRIBUTING.rst
    ├── LICENSE.md
    ├── script
    │   ├── __init__.py
    │   └── script.py
    ├── project.cfg
    ├── requirements.txt
    ├── README.rst
    ├── setup.py
    ├── MANIFEST.in
    ├── tests
    └── tox.ini

Folder Structure for Python Modules
======================================

This folder structure is defined by the cookiecutter project
`stored here. <https://gitlab.driveline.gkn.com/cookiecutter-templates/modules>`_

::

    project
    ├── AUTHORS.rst
    ├── docs
    ├── HISTORY.rst
    ├── CONTRIBUTING.rst
    ├── LICENSE.md
    ├── module-name
    │   ├── __init__.py
    │   └── module-name.py
    ├── project.cfg
    ├── requirements.txt
    ├── README.rst
    ├── setup.py
    ├── MANIFEST.in
    ├── tests
    └── tox.ini


########################
Setup and Installation
########################


All python projects shall be :term:`pip` installable.
Use the :doc:`setuptools package <setuptools:index>` to define the
``setup.py`` file and build wheels for all platforms.

.. note::

    For command line tools in python, use :term:`pipsi` instead of pip to
    enable the deployment of the cli. See this
    `readme <https://github.com/mitsuhiko/pipsi#readme>`_ to understand more.

#####################
Virtual Environments
#####################

All python development shall be done using virtual environments with the
corresponding python version. The ``requirements.txt`` shall contain a list
of all the modules used for the project and the dependent versions shall
clearly be marked. All wheels corresponding to these shall be downloaded and
cached at the local pypi server `here. <http://pypi.driveline.gkn.com>`_

####################
Testing Frameworks
####################

Tests will be written using :doc:`pytest <pytest:index>`.
:doc:`The unittest library <python:library/unittest>` may be used if working on code
that is not Python 2.7 or 3.7+ compliant. However,
:ref:`this is not encouraged <py23>`.

:doc:`The hypothesis library <hypothesis:index>` may be used where data
plays a large role in the program. Representational data may be generated
using the :doc:`faker <faker:index>` library.

.. note::

    All text-based fields must be tested to support all *latin-16* characters.

##################################
Command Line Interface Frameworks
##################################

If the task calls for command line interfaces, the use of
:doc:`sys.argv <python:library/sys>` is *discouraged*.
Developers are directed towards the :doc:`click <click:index>` module for
creating :term:`CLIs <cli>` development.

#####################################
Graphical User Interface Development
#####################################

To develop a user interface, Python GUI frameworks are discouraged.
All user interfaces must be developed with a **web-first** philosophy
using :term:`Electron`,
:term:`html` and :term:`ES6 Javascript <ecmascript>`.

**************************
nodejs and npm
**************************

All webpages shall be developed using `nodejs <https://nodejs.org>`_ and
`npm. <https://www.npmjs.com/>`_ The  `vue.js, <https://vuejs.org/>`_
framework must be used to build visual components and
the `bulma <http://bulma.io>`_ library for the *css*.

SASS/SCSS files for company colors and branding are served at the
`CDN <https://cdn.driveline.gkn.com>`_.

.. admonition:: Under Consideration (Evaluation Ongoing)
    :class: warning

    nodejs and npm are under evaluation, and the results look favourable.
    However, the choice of the JS framework, vue.js, currently, is under
    evaluation. React.js might be the better choice, but this has not been
    considered so far.


.. admonition:: Future Prospects
    :class: note

    If an application requires mobile or tablet interfaces Cordova or
    React Native shall be used.


**************************
CUDA C
**************************

Processor-heavy application logic shall be coded in CUDA C.

**************************
Ruby
**************************

Easy Redmine plugins alone will be coded using Ruby. Coding microservices using Ruby on Rails is discouraged.

------------------------------
Databases
------------------------------

********
MySQL
********

MySQL is the database of choice as of this current edit. 

.. admonition:: Future Prospects
    :class: note

    Plans are underway to move everything to
    `PostgreSQL. <https://www.postgresql.org/>`_

************
PostgreSQL
************

.. admonition:: Under Consideration (Evaluation Pending)
    :class: warning

    The Relational database of choice for the foreseeable future will
    be PostgreSQL. However, for the current timeline, MySQL is being used.

************
MongoDB
************

`MongoDB <https://www.mongodb.com/>`_ is the NoSQL database of choice.
The corresponding :doc:`mongoengine <mongoengine:index>` python library
will be used as a wrapper of choice.

----------------------------------------------
Message Queue
----------------------------------------------

******************
RabbitMQ
******************

All messages shall be passed using the Publisher/Subscriber model using
RabbitMQ. Messages must be retained for a period of 3 months.

.. admonition:: Under Consideration (Evaluation Pending)
    :class: warning
    The retention period is not writ in stone. However, depending upon the
    number of messages that are expected as of this build (|today|), 3 months
    seems to be an optimum selection.

---------------------------
Cache Store
---------------------------

*******************
Redis
*******************

`Redis <https://redis.io/>`_ is the cache of choice.
Do not use Redis for message storage, however.

.. admonition:: Under Consideration (Evaluation Pending)
    :class: warning
    Redis was chosen plainly because RabbitMQ + Redis is a popular
    combination. However, memcached might be chosen instead depending upon
    future development and program complexity.

----------------------------
CI/CD
----------------------------

****************************
Jenkins
****************************

`Jenkins <https://jenkins.io>`_ must be used for running
all build scripts as well as the Continuous Deployment scripts.
`This Jenkins server <https://cae.driveline.gkn.com/jenkins>`_ must
be used for all production builds. Local Jenkins deployments may be used by
developers for personal usage.

.. admonition:: Under Consideration (Evaluation Ongoing)
    :class: warning

    Jenkins is currently being evaluated on a Windows machine. It will be
    further evaluated on a linux server.

    Gitlab-CE is also being considered as CI/CD tool, but not to *replace*
    Jenkins. So far, Jenkins has been found favourable and easy enough to
    configure, so Gitlab-CE's CI/CD features may only be evaluated for a sense
    of understanding what additional features it provides.

----------------------------
Containerization
----------------------------

***************************
Docker
***************************

All automated builds and containers must use docker. 
All microservices, which do not rely on the GPU directly,
shall use docker containers.

Docker images must be stored at the
`local docker registry <https://cae.driveline.gkn.com/docker-store/>`_. All
public images which are *sub-classed* must be locally stored as well.

This flow must be orchestrated via Jenkins.

.. note::

    Look into performances for CUDA code on docker containers. I suspect that the code will run at almost
    native speed through docker.

----------------------------
Orchestration
----------------------------

**************
Docker Swarm
**************

Docker containers for microservices or automated builds will be deployed using docker swarm.

**************
Apache Mesos
**************

`Apache Mesos <http://mesos.apache.org/>`_ must be used for deploying any containers and/or services on remote servers.

.. admonition:: Under Consideration (Evaluation Pending)
    :class: warning

    Evaluate mesos for deploying and orchestrating non dockerized services, as well as dockerized services.

------------------------------
Service Discovery
------------------------------

*********************
Consul
*********************

-------------------------------
Search Services
-------------------------------

*********************
ELK Stack
*********************

.. admonition:: Under Consideration (Evaluation Ongoing)
    :class: warning

    Elasticsearch, Logstash and Kibana are being evaluated to see if they are suitable for search services.

*********************
Apache SOLR
*********************

.. admonition:: Under Consideration (Evaluation Pending)
    :class: warning

    Apache SOLR may be selected/evaluated later if Elasticsearch proves to be a performance related issue.

.. warning::

    Do not use Elasticsearch or SOLR as a primary data store.
    All the data that is indexed must be stored in MongoDB primarily.
    The search services just provide the indexing.

-------------------------------
Provisioning
-------------------------------

******************
Ansible
******************

Ansible is our solution of choice when it comes to provisioning servers.
All installations and should happen through Ansible playbooks.
This ensures that the installation process is recorded and version-controlled.

------------------------------
Log Services
------------------------------

**********************
Logstash
**********************

:ref:`See note above <elk>` related to the ELK stack.
