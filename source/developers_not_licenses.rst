======================================
After-Afterword: Inhouse Development
======================================

.. sectionauthor: Vinay Keerthi

.. warning:: 
    
    What follows is largely a personal opinion. It can be argued that code shouldn't be developed inhouse, especially
    when high stakes are concerned, and that paying for a license, and thereby offloading the responsibility enables
    a company to take one weight off its shoulders. However, there is a lot to be said for being able to develop 
    your own software in today's world. It enables rapid change.

    This entire section is mostly a love-song to developing code inhouse, building software products with the same
    vigour and tenacity that fuelled the industrial revolution, for instance. It may be skipped if that sort of thing,
    *i.e.* passion, bores you.

..

    **"Not all engineering companies are software companies."**

That line of thought is a valid argument. Developing software is serious business. **Not all companies need to write their
own software.** This author completely agrees with this. However, there is an argument for a *semantically loose* converse.

..

    **"All companies need to be able to write their own software, when they need to."**

Software that concerns business logic needs to be developed inhouse. It requires years of understanding of the business process,
continuous improvements and additional features. While there are software that can be *customized* to suit a company's needs,
oftentimes, it is better to write core functionality inhouse. Customizing readily-available software also needs to be conducted
in lines with production-grade software practises, as outlined in the :ref:`practises` section earlier.

-----------------------------
Outsourcing Software Work
-----------------------------

A company should view the software it uses internally to enable and orchestrate business logic as a core knowledge. Just because a company does not
sell software does not mean it should not invest in software development.

Think of it this way. Small engineering tasks are outsourced, but never drastic design-changing decisions. Why?

The software that empowers a business must be deployed, maintained and, if possible, developed entirely inhouse. This is very critical because in today's world,
software is a unique form of currency. It is not that we must shun all commercial software. No. There are software we cannot write. However, there is a lot of software
we can and should write internally. Outsourcing core business software ensures that the knowledge of its innate features is never capitalized. The things we could
glean from developing such software internally is lost to a third-party company.

--------------------------------
Freedom to Choose Tools
--------------------------------

Developers should be given free reign to select their own tools. This has been stated earlier in this document, but it begs repeating. *Developers*
should choose the tools they work with. It is akin to a sculptor picking a chisel. It is understandable that a business that deals with decades, not weeks, worries about rapid change but this is exactly why developers should be able to pick their tools.

For example, a CI/CD platform can recognize and register dependency versions. If a service developed today needs to run in 20 years' time, a CI/CD platform will
enable innate version control and provisioning of the dependencies. You will not need to worry about getting a piece of software to work. If it works today, it will
work in ten or twenty or thirty years.

This is enabled by a developer choosing the tool he needs for deployment. Of course, the business has every right to define and demand a process for this. But the
developer, not the business should pick the tools.

.. note:: 

    Think of this in an analysis engineer's terms. Perhaps you assume that a tool in software development is like the software analysis or design engineers
    use for their daily work.

    This analogy is wrong. This analogy does not work. It is not to say that an analysis engineer's tools are not important. No, but it is to say that their tools
    are sometimes driven by business needs, customer agreements and contracts.

    A developer's deployment pipeline, his text editor, the version control system, should not be held back because of a business case.


A software developer's tools are not the same. Mostly because this is an industry where the free tools are leagues ahead of the licensed tools. There is no price
for the GNU C compiler. Yet, with it, you can write code that will run on a washing machine. There is no licensing fee for git, and with it, you can manage thousands of versions of your code base in a small repository size, enabling a global team.

Linux is free, and with it you can build systems that garner to thousands and tens of thousands of requests on a relatively weak machine.

Granted, the developers must not change their CI/CD pipeline every other week, or even once in six months because something shinier has come about. However,
asking them to shift paradigms from `git` to `SVN` or from their editor of choice to a company-selected code editor is not going to get the work done quicker.
It will definitely slow it down.

You do not need to pay for software licenses in the development world. Almost all the tools are free, like air. Just hire the right people and let them do their thing.
