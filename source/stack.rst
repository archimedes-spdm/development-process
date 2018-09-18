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

#################################
Python Project Folder Structure
#################################

All standard tasks have well defined folder structures which are to be replicated using :term:`cookiecutter` templates.
These templates can be found in the appropriate repository and can be deployed using the steps detailed in the 
`cookiecutter documentation <https://cookiecutter.readthedocs.io>`_.

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

This folder structure is defined by the cookiecutter project stored `here <https://gitlab.driveline.gkn.com/cookiecutter-templates/cli>`_.

.. note::

    For command line tools in python, use :term:`pipsi` instead of pip to enable the deployment of the cli. See this
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

This folder structure is defined by the cookiecutter project stored `here <https://gitlab.driveline.gkn.com/cookiecutter-templates/modules>`_.

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


All python projects shall be :term:`pip` installable. Use the `setuptools <>` module to define the ``setup.py`` file and build wheels for all platforms.

.. note::

    For command line tools in python, use :term:`pipsi` instead of pip to enable the deployment of the cli. See this
    `readme <https://github.com/mitsuhiko/pipsi#readme>`_ to understand more.

#####################
Virtual Environments
#####################

All python development shall be done using virtual environments with the corresponding python version. The ``requirements.txt`` shall contain a list of all
the modules used for the project and the dependent versions shall clearly be marked. All wheels corresponding to these shall be downloaded and cached at the
local pypi server `here <http://pypi.driveline.gkn.com>`.

####################
Testing Frameworks
####################

Tests will be written using :ref:`pytest <pytest:genindex>`, :ref:`unittest <python:unittest>` or :ref:`hypothesis <hypothesis:genindex>`.

py.test is encouraged wherever possible.

##################################
Command Line Interface Frameworks
##################################

If the task calls for command line interfaces, the use of :ref:`sys.argv <py:sys.argv>` is *discouraged*. Developers are directed towards the
:ref:`click <click:genindex>` module for creating :term:`CLIs <cli>` development.

#####################################
Graphical User Interface Development
#####################################

To develop a user interface, Python GUI frameworks are discouraged. All user interfaces must be developed with a **web-first** philosophy using
:term:`Electron`, :term:`html` and :term:`ES6 Javascript <ecmascript>`.

**************************
Web Development
**************************

All webpages shall be developed using React, npm and bulma css. SASS/SCSS files for company colors and branding are served at the `CDN <https://cdn.driveline.gkn.com>`_.

If an application requires mobile or tablet interfaces React Native shall be used.


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
MySQL is the database of choice as of this current edit. Plans are underway to move everything to PostGreSQL

************
PostGreSQL
************

The Relational database of choice for the foreseeable future will be PostGreSQL. However, for the current timeline, MySQL is being used.

************
MongoDB
************
MongoDB is the NoSQL database of choice. The corresponding :ref:`mongo-engine <mongoengine:genindex>` python library will be used as a wrapper of choice.

----------------------------------------------
Message Queue
----------------------------------------------

******************
RabbitMQ
******************

All messages shall be passed using the Publisher/Subscriber model using RabbitMQ.

---------------------------
Cache Store
---------------------------

*******************
Redis
*******************
Redis is the cache of choice. Do not use Redis for message storage, however.

----------------------------
Orchestration
----------------------------

**************
Docker Swarm
**************

**************
Apache Mesos
**************

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
Elasticsearch, Logstash and Kibana are being evaluated to see if they are suitable for search services.

*********************
Apache SOLR
*********************

Apache SOLR may be selected/evaluated later if Elasticsearch proves to be too heavy a choice.

.. warning:: 

    Do not use Elasticsearch or SOLR as a primary data store. All the data that is indexed must be stored in MongoDB primarily. The search
    services just provide the indexing.

-------------------------------
Provisioning
-------------------------------

******************
Ansible
******************

------------------------------
Log Services
------------------------------

**********************
Logspout
**********************

**********************
Logstash
**********************

