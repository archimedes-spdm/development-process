==========================
Automated Provisioning
==========================

.. todo::

    Update this section so that it talks about what follow and not why we follow this. Move justification to the Process Selection and Justification document.


:term:`Provisioning <provision>` is a software development term which talks about the installation, configuration and management of software from a
system administrator's perspective.

During software development, it is important for a programmer to capture the :term:`dependencies <dependency>` of his or her program in an easy-to-:term:`parse` manner.
This makes is easy to install software later on.

Automated provisioning is sort of a policy-based management methology. Rights and accesses can be assigned to roles, machines can be tagged with specific roles as well,
and the related software will be deployed there.

.. image:: /_static/provisioning/automated_provisioning.png
    :height: 400
    :align: center

*Illustration: Manual Provisioning vs Automated Provisioning*

.. seealso:: `This Wikipedia Page on Infrastructure as Code <https://en.wikipedia.org/wiki/Infrastructure_as_Code>`_ is recommended to readers to understand why even configuration should be stored in machine-readable formats.

Automated provisioning provides us the ability of deploying a service after ensuring that everything it needs to safely run are installed and accessible.
Traditional methods of provisioning involve manual installation of software. This involves several people, with several different chains of approval and
authorization. Sometimes, this system takes days, weeks or months to install a simple application on a user's workstation.

With automated provisioning tools such as `Ansible <https://www.ansible.com>`_, it is possible to ready a workstation automatically, as opposed to having someone configure
it manually. The same stands for software, of course.

All configuration and provisioning *must* be done through automated provisioning tools, so when a service needs to be moved to another machine, or when software
needs to be installed on a new machine, all that a System Administrator needs to do is sit back and watch as the corresponding software is installed, automatically,
based on a user's groups or a machine's specifications.

This ensures that no knowledge regarding machine configuration is lost when employees leave or are unavailable. All roles and configurations are version controlled,
and they can be replicated in moments.

-----------------------------------------
Automated Provisioning and Businesses 
-----------------------------------------

Automated provisioning can also be tied in with business requirements.

If an employee is added to a project, then all the relevant software should be deployed to his workstation without the need for raising tickets manually.
This saves time and paperwork. In addition, the system administrator does not need to worry about the user's space requirements. If there is not enough space,
the system can schedule an upgrade so that the user has as much resources as he needs to **get the job done.**
