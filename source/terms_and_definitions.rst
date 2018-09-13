========================
Glossary
========================

.. |RST| replace:: ReStructuredText

.. glossary::

    Python
        Python is a high-level programming language. The most common form of python is written in C, and it is considered to be a very easy language to learn. Python is the preferred language of choice at many companies where data science is concerned. It is also used to make server-side scripts, develop interfaces or to automate workflows.

    Sphinx
        Sphinx is a tool that makes it easy to create intelligent and beautiful documentation. It was originally created for the Python documentation, and it has excellent facilities for the documentation of software projects in a range of languages.

    RST
        |RST| is an easy-to-read, what-you-see-is-what-you-get plain text markup syntax and parser system. It is useful for
        in-line program documentation (such as Python docstrings), for quickly creating simple web pages, and for standalone
        documents. |RST| is designed for extensibility for specific application domains. The |RST| parser is a component of
        Docutils.

    SVN
        Subversion is a Version Control Software that is used at many companies, including GKN. See the :ref:`svn` to understand more.

    Version Control Software
        Version Control Software is used by software developers to manage changes to documents, code, scripts or configurations. It is a crucial part of software development process.

    git
        git is a distribution version control system that was developed by Linus Torvalds, the creator of the Linux kernel.

    commit
        A commit is an action developers take when they wish to submit their changes to a code file for version control. By *committing* something, a
        developer is saying he or she wants the version control system to remember these changes. Commits record the changes that files underwent, the timestamp
        for the changes as well as the author of the changes. Multiple developers can send commits which can have "conflicts" with one another.
        It is then the responsibility of the developers to sort out their commits so that the codebase is clean. As many files as required can
        be committed in one commit. A list of commits is a list of recorded changes to a file or files.

    push
        A push is an action developers take when using distributed version control systems, when they want to submit their local commits to the global repository.

    repository
        A version control repository is a central storage area wherein code changes are recorded. There are two types: distributed, and central.

    checkout
        A checkout is an action developers take when they are "downloading" a version of code from a repository to their local machine. Every developer will need to checkout a repository before they can begin working on it.

    clone
        cloning is another term for checkout.

    update
        When a developer requests for an update of his local code repository, he is asking the central storage area for all new changes to the files, from the time of the last update or the original checkout time. This pulls the files, checks the files for differences, and writes in additional lines into the code. It is not as simple as just copying over the new version of the file. Version control software will download the changes and add the changes into one's local directory.

    pull
        Pulling is another term for update.

    branch
        A branch, in software version control terms, is like a tree branch, with a major difference. A branch of code is a codebase with a separate commit history
        from that moment on. Developers must always branch their code and then merge branches so that the changes are always grouped and committed only when stable.

    fork
        A fork is similar to a branch, but it is a largely git-centric term.

    tag
        A tag, in software version control terms, is a label given to a collection of commits for easy retrieval. It helps logging and management of the codebase.

    provision
        To provision software involves the complete cycle of identifying what software must be installed, including the dependencies, identifying how to install the software, scheduling the actual installation, verifying installation.

    parse
        When code *reads* something, like text, it is said to be "parsing" it.

    dependency
        A software dependency is a requirement that needs to be fulfilled (another software or configuration) before a software can be installed completely. Without fulfilling a software's dependencies, 100% functionality cannot be expected.

    Github
        A web-based hosting service for git repositories. It provides bug tracking, feature requests, task management and wikis. Cloud based is free. On premises installation is paid. Owned by Microsoft as of June 04, 2018. `Github.com <https://github.com>`_

    GitLab
        A web-based Git repository manager that has in-built wiki, issue-tracking and CI/CD pipeline features. Can be installed on premises for free. `Gitlab.com <https://gitlab.com>`_
    
    Jenkins
        An automation server that helps automate the deployment, delivery and integration part of the software development process. Can be installed on premises for free. `jenkins.io <https://jenkins.io>`_
