.. _vcs:

==================================================
Source Code Management: Version Control Systems
==================================================

------------------
Understanding VCS
------------------

Source Control is a way for developers to manage their source code. All code in a company of any size should be under source control. However, the choice of the source control protocol used determines the level of freedom/control available to developers and source code managers.

Native filesystems offer some minor form of version control, but advanced systems offer much greater control over the versions and how they can be retrieved. Even legacy systems have always been developed using some form of source control, be it CVS, Mercurial or Git.


.. image:: /_static/vcs/1.png
    :align: center
    :height: 400

*Illustration: Version Control Systems*

This section presents a case for :term:`git`, and why it is superior at letting developers do what they're best suited to do: **code**. :term:`git` gets rid of the ugly facets of version control, and it keeps developers focussed on the code.


.. admonition:: Terms
    :class: tip

    There are a few terms that you should acquaint yourself with when dealing with version control. The following links will direct you to the glossary section,
    where you can read more about these terms.

    :term:`commit`, :term:`push`, :term:`checkout`, :term:`clone`, :term:`update`, :term:`pull`, :term:`branch`, :term:`tag`

------------------------------------
Centralized Version Control Systems
------------------------------------

A centralized version control system is a server that sits somewhere on your company's network, and hosts a complete repository. At any given point of time, all code changes that are :term:`committed <commit>` are :term:`submitted <push>` to the central repository. This system of version control was largely the industry standard throughout the 80s, the 90s and early 2000s. Many companies continue to rely on central version control systems, and they are satisfied with the behaviour of such
a system.

.. image:: /_static/vcs/central_vcs.png
    :align: center
    :height: 300

There are two well-known central version control systems, CVS and SVN.

.. cvs:

#####
CVS
#####

.. _svn:

############
Subversion
############

..

    "Subversion is CVS done right."


------------------------------------
Distributed Version Control Systems
------------------------------------

A distributed system allows users to work at separate sites, at lightning speed. A Centralized Version System points back to a server that has the latest code, all the time. Every developer has to deal with each other's commits, a broken master branch is not easily fixable, and it is a nightmare to deal with branches from different sites. In a distributed environment, it is trivial to code in an environment that is at once isolated and team oriented. You commit your changes locally, in a copy that has all the changes from the master branch (or any branch that you pull in, really), and you get the freedom to push back your changes in one go, once everything is tested.

.. 

    "Distributed Version Control Systems [are] possibly the biggest advance in software development technology in the [last] [twenty] years"

        **Joel Spolsky**
        
        [SPOLSKY]_

.. image:: /_static/vcs/dist_vcs.png
    :align: center
    :height: 300

The concept of a distributed version control system was developed to solve the problem that Linus Torvalds faced in developing the Linux Kernel. This in turn led
to the development of :term:`git`, the world's most popular version control system.

With a DVCS, developers can write scripts at their end, to run tests, or run scripts at the server end, to check for protocols that should be addressed. A distributed system is so much more faster because every developer has a local copy. You can scale your development team overnight and still be able to deal with noncompliant code because your new developers made a mistake. A broken branch doesn't stop the production server from doing its job.

Alternately, if a project's description changes overnight and there is a major code overhaul, smaller projects relying on the old code base don't need to worry about losing their required code. They can branch it off, and continue working.

Say you're managing a large codebase that needs a new feature for a new project that may not be required for other projects. You can create a branch, write in that new feature, and have it exist completely secure in its own branch, only taking what is explicitly required from the master branch. And you can have someone manage the master branch, having only the approved features in it so that it is always approved and only authorized people can write to it.

Using feature branches is not only more reliable than directly editing production code, but it also provides organizational benefits. They let you represent development work at the same granularity as the your agile backlog. You could map requests to Jira tickets so that they are addressed in their own branches, for instance.

.. git:

####
git
####

Git was created by Linus Torvalds to help Linux Kernel developers around the world collaborate together on the code. Developers around the world agree that git has become the defacto source control tool of choice. Offering git to developers brings in a mindset that encourages experimentation and collaboration.

Lone developers and teams both win when offered the chance to work with git. When a company allows developers to use git, it is a sign to possible future employees that this company allows the very best tools and lets them learn cutting edge technology when it comes to software development. Limiting developers to technology that is bound behind paywalls reduces that and cripples their motivation and interest.

***********************************
Working Together as a Community
***********************************

.. image:: /_static/vcs/working_together.png
    :height: 350
    :align: center

Git also makes it possible to work together as a team across different environments because it works on Linux and Windows. It is just as fast on
the smallest of ARM processors.

With git's vast infrastructure of tools, it is easy to build a team that talks and breathes together through their code.

If you've had a developer who had to take a sudden sick leave, using a tool like Github Enterprise, Bitbucket or Gitlab will ensure that the community goes on, without losing the pace. All the documents related to the code are accessible by those who are authorized. Some people can have read access, some can have write access, everything can go through a streamlined authorization platform.

Git works, quite simply.

*************
Git is Safe
*************

Did your version control server suddenly go offline? Did you have to move the server and are you tasked with repointing all your checkouts?

This is no problem with git. You can work offline, or on the go. With git you can make changes locally, push your changes when the central server is available and then have your source code manager merge the changes as per his or her process.

Did someone make a mistake? Easy peasy. Fix mistakes with git's undo commands. Correct last commits, undo an entire commit. Git leaves a trace, always. So you can even undo your undo.

************************
Git is an ecosystem
************************

By using git, we get in an entire ecosystem of developers who love working with the tools we use. CVS is outdated, and SVN is largely following suit. A large community often is an advantage by itself because an ecosystem evolves around the system. Lots of tutorials, tools, and services make Git even more attractive.

**Github Enterprise** or **Gitlab** go one step beyond. It offers the power of github's vast architecture and learnings in an enterprise server. Offering
**Github Enterprise** or **Gitlab** encourages developers across all our sites to collaborate and talk to one another about code. Engineers can search for tools,
publish their tools and have them accessible by others like them across the world.

If the price is too high, Gitlab is a freer alternative. Both offer power that no other solution can match, especially not one centered around Centralized Version Control Systems.


***************************************
Branching in Git vs Branching in SVN 
***************************************

.. image:: /_static/vcs/feature.png
    :height: 250
    :align: center

SVN - Branches on SVN are treated as normal folders on the repository. As you have only the central repository
every branch is automatically remote and public (every user with access to the repository will have access to the
branch). On the other hand, one can checkout the branch on a different folder on it’s file system independent
of having the trunk of the repository checked-out. Another option is also start a branch on justa a subfolder of
the repository. Branches on SVN are basically copies of the affected folders and this copy can be made locally
and then commited to the central repo or remotly. On the remote copy it is made a Cheap Copy of the targeted
files, this means that it is only a reference for the original files and not a actual file, this way the repository stay
as lean as possible.

..

    "Subversion has no internal concept of a branch—it knows only how to make copies. When you copy a
    directory, the resultant directory is only a “branch” because you attach that meaning to it. You may think of
    the directory differently, or treat it differently, but to Subversion it’s just an ordinary directory that happens
    to carry some extra historical information... Subversion’s branches exist as normal filesystem directories
    in the repository."
    
    [COLLINS1]_

GIT - Branches are pointers to specific commits on the repository. They are created locally and can be
pushed/pulled to/from a remote repo or not.

Git *understands* branches. It is possible to pull specific branches and have entire business logic coded into specific branches which can then be 
merged after separating the logic. This way of development helps Test-Driven Development, and it also helps developers maintain control over their code
and their commit choices.

------------------------------------------------------------
A Global Team Cannot Rely A Central Version Control System
------------------------------------------------------------

.. image:: /_static/vcs/git.png
    :height: 150
    :align: center

.. seealso::
    `This Youtube talk <https://www.youtube.com/watch?v=4XpnKHJAok8>`_ by Linus Torvalds, the creator of 
    :term:`git` provides an argument for the use of git. Readers are recommended to watch it.

.. admonition:: Personal Viewpoint
    :class: warning

    This piece is largely opinionated, but it is done in a positive vein.
    
For a moment, consider these questions:

1. Does your team work across complex network definitions?
2. Do developers have multiple accounts across businesses, multiple email-addresses?
3. Do your developers work across the world?
4. Do your developers face network issues, access issues or the like?
5. Does your code solve problems **across** businesses?
6. Have you ever looked at solutions that another site has developed and thought to yourself: "How did they implement this? Can I bring this learning to my team?"
7. Have you ever been stuck with a problem, wished there was a script to solve this problem and been unable to search your entire organization's code bases to find a properly documented project that does the exact thing you want to solve?
8. Have you had novice developers break codebases because they didn't know what the coding standards were, or what issues need immediate attention?
9. Have you wondered how to automate tests along your organization?
10. Have you wondered how to deploy software with a pipeline, automatically?
11. Have your developers ever wanted to conduct AB testing of code, deploying on a test server, checking their tests and usecases, and only then deploying to the production codebase?

These things *can* be done with a centralized version control server, but at extreme difficulty. It is not this author's intention to say it is impossible with CVS or SVN, but there is a large, **glaring** difference.

Git comes with a plethora of free tools, tools which have been tested through the dirt and the grime by companies with more experience and expertise.

Developers should not have to deal with a handicap when developing code. Quite frankly, CVS and SVN are handicaps to developers.
There is a reason why ``git`` has become the standard. It is a no-nonsense tool that has outdated everything else.

If we are to excel, it is the opinion of this author that to excel, we need ``git``.

