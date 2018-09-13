===================
Automated Testing
===================

A test is a series of operations conducted to verify if code works as it is intended to. Tests are written to reaffirm the behaviour of code, to understand if
their execution has changed over time. Tests are the fundamental component of Test-Driven Development.

----------------------------
Tests Should be Automated
----------------------------

There are many components of software that are manually tested. However, **all testing should be automated**. As a company, we should strive towards a high test
coverage, and a 100% automated test pipeline. Automated tests help preserve the expected behaviour of code in the main repository. 

******************************************************************
Tests Should Be Written by the Developer Working on the Feature
******************************************************************

As stated in the TDD philosophy, no code should be written without first having written the tests for it. In line with that idealogy, the developer who is working
on a piece of code must write the tests. Offloading tests to another developer or another team is not a lean process.

********************
Data-Centric Tests
********************

Wherever data is concerned, tests are surely affected. To offset the effects of data changes, whenever data-centric code is written, the tests should take
the nature of the data into purview before the development begins. The developer should write tests that assess the data itself, to gauge whether it is
acceptable and falls in the buckets which the developer assigned them to in the beginning. These tests should also define how to generate *faux* data for testing purposes, what assumptions were made regarding the data, and how they can be emulated.

.. seealso:: To understand what we mean here, go through the documentation for the Haskell 
    library `Quickcheck <http://www.cse.chalmers.se/~rjmh/QuickCheck/manual.html>`_, or the documentation for 
    a similar python library `Hypothesis <https://hypothesis.readthedocs.io/en/latest/>`_.

********************
Data-Agnostic Tests
********************

The same tests should also define how to test the expected behaviour without depending on the data. If there is business logic involved, this should be defined
in terms that are measurable for a *faux* dataset, and expected results should be recorded and reproducible.

The two forms of testing discussed above will ensure that testing is conducted to assess both the algorithm itself as well as the dataset it is used upon. This way,
when the nature of the standard dataset changes, or when external APIs fail, these test will yield meaningful responses, which can be capitalized upon.

**********************
User Interface Tests
**********************

User interfaces should be tested automatically as well. For web interfaces, extensive Selenium tests must be written, to describe the user's expected usage, as 
well as to measure the amount of time the APIs take for response.

Desktop clients should be written, again using TDD, so that they can be tested automatically. There is no scenario in which manual testing of interfaces should be 
conducted in today's day and age.

--------------------------
Automated Testing Systems 
---------------------------

There are many tools to perform automated testing. Two of these are Jenkins and Gitlab.

*********
Jenkins
*********

Jenkins is a tool to automate just about anything. It is commonly used to integrate continuous tests, integration services and to run automated builds. Developers can use Jenkins to deploy code, run their tests or create installers once a particular branch has received a push.

********
Gitlab
********

Gitlab and Github Enterprise both come with automated testing frameworks. Gitlab in particular is easy to set up on our local premises,
with complete control over its data and orchestration.

