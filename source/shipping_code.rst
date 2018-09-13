=================
Shipping Code
=================

This document speaks about how code is shipped to the right servers, how executables are created and how users receive the right tools that they need once
they are added to a project.

--------------------
Deploying Services
--------------------

A service is a script that runs on a server somewhere. It needs to run on a specific kind of machine, and has to be integrated with existing authentication
and security protocols.

In today's development scenario, services are orchestrated and deployed using tools such as `Docker Swarm <https://docker.com>`_,
`Mesos <http://mesosphere.com>`, or `Kubernetes <https://kubernetes.io>`_. This ensures that the act of deploying services on an appropriate machine
is taken away from a developer's todo list and representated as configuration files. These files tell the tool where to deploy their service.


.. image: /_static/shipping/docker.png
    :align: center
    :height: 500

*Illustration: Docker Swarm In Action*

Such a deployment methodology ensures that services can be deployed automatically. Shipping code, in simple terms, has become an automated process.

Developers commit and push changes to the production branch of the repository, the CI/CD platform orchestrates the tests. Upon success, the code is then delivered to
the deployment platform which decides where the code must then run.

This practise also enables horizontal scaling of infrastructure. By adding more machines, additional services and scripts can run effortlessly without the developer
having to reconfigure entire machines and production environments. This also facilitates rollbacks to previous versions, user experience testing, AB testing, 
and **design of experiments.**

-----------------------------
Delivering Updates to Users
-----------------------------

The previous section spoke about deploying server-side code. Code that runs on machines that are controlled by developers. However, there is the other side.
Client side code is usually in the form of interfaces to server-side code. These are either command line tools, or GUIs made for specific tasks, or some automation
scripts that help users in their daily tasks.

CI/CD platforms and provisioning tools such as Ansible, Chef or Puppet make it easy for users to get the code they need as soon as they are added to a new role.

For example, if a particular project involves a set of scripts that the user needs access to, just adding the user to the project will then trigger a task that delivers
the right software and scripts to his machine so that he can begin working immediately.

