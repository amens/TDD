Test Driven Development Research Notes
======================================

Uncle Bob's Three Laws of TDD [[1]][1]
--------------------------------------

 1. You are not allowed to write any production code unless it is to make
    a failing unit test pass.
 2. You are not allowed to write any more of a unit test than is sufficient
    to fail; and compilation failures are failures.
 3. You are not allowed to write any more production code than is sufficient
    to pass the one fialing unit test.
 4. You are not allowed to write untestable code (user comment).

It follows that

 - you can't spend much time writing *only* tests or *only* code,
 - the system is constantly in a cycle of compiling and executing,
 - you need tooling that supports this (often closely related to the
   language itself; i.e. C or C++ make this difficult.)

The goal of all this is to have code that is almost always working – you
don't need to waste time debugging.

Summary
-------

TDD is only a part of the Agile development technique. It consists of *test
first development* (TFD) and *refactoring*.

### Methods

 1. Think about what you want to do.
 2. Think about how to test it.
 3. Think about the desired API.
 5. Write just enough test code to make it fail. Watch it fail.
 6. Write just enough functional code to make it pass the test.
 7. Refactor, deduplicate, make more efficient, etc.
 8. Run the test suite. If it passes, go to 1, else continue.
 9. Try to fix the introduced problem, or revert, then go to 8.

### Side Effects

 - You are probably going to have more LOC for tests than for the functional
   code. [[2]][2] [[3]][3]

### Benefits and Strengths

 - a creation of hundreds and thousands of tests, which can be run at any
   time, because they all should be passing;
 - transparency in the code;
 - tests that act as documentation and code examples, they are always
   up-to-date;
 - a testable design and code base, because the TDD technique forces the
   design to be testable;
 - the ability to refactor at will, because the tests cover all the code
   paths and functions;
 - no fear of touching the code or deleting code, the code becomes malleable
   (again) and makes it a lot *softer* again. [[1]][1]

### Requirements

In order for TDD to really make sense, all the following points must hold.

 - You are writing code that is testable in a unit-test manner. [[4]][4]
 - That what you are developing has an obvious approach and will not require
   extensive prototyping or experimentation. [[4]][4]
 - That you will not need to refactor too heavily or change the
   specification unless you have the time to repeatedly rewrite hundreds
   or thousands of test cases. [[4]][4]
 - Nothing is sealed. [[4]][4]
 - Everything is modular. [[4]][4]
 - Everything is injectable or mockable. [[4]][4]
 - That there is something of benefit to test at a unit test level. [[4]][4]
 - The management and the development team must accept and apply TDD
   thoroughly. [[4]][4]
 - That your organization places a high enough value on low-defects to
   justify the resource sink [[4]][4]

### Weaknesses

The requirements above may also be seen as weaknesses.

 - Certain software modules or projects are less suited to TDD than others,
   for example projects that are focussed around
    * user interfaces,
    * networking,
    * external interaction,
    * etc.
   Also consider the requirements that a project must fulfill to be fully
   compatible with TDD.
 - Converting legacy projects to TDD can involve a huge amount of work
   – there is no guarantee that all code paths are covered or that the tests
   consider all the cases that have been covered in the code.
 - Seeing hundreds or thousands of passing tests can create a sense of false
   security. [[4]][4]
 - Even trivially changing or heavily refactoring the functional code can
   involve rewriting hundreds or even thousands of tests. [[4]][4] [[5]][5]
 - Requires a huge investment in time to *get into it*, thus it also
   requires a lot of discipline. This can be hard to sell to other
   developers. [[5]][5]
 - Selling the full TDD package to management can be very hard. For example,
   TDD is best done with pair programming, which many managers cannot
   accept. [[5]][5]
 - You lose a lot of (possibly negative) freedom, because TDD is very rigid
   and specifies much of the software development process. This might be
   an advantage, but some certainly won't like it. [[5]][5]
 - Applying TDD *does* require an extra time and resources investment. This
   may be worth it, depending on what you are doing, but it still is a big
   investment. [[5]][5]
 - TDD can lock the functional code into a certain design as long as tests
   assume a certain API. If the API is not yet certain or clear, or
   prototyping must be done, then TFD will generate extra work. [[5]][5]
 - TDD makes tweaking and tuning (like algorithms) much more expensive.
   [[5]][5]
 - The entire set of tests must be maintained and debugged. While the tests
   only help make sure the functional code is good, you still are completely
   responsible for the quality of the tests. Many people do not know how to
   properly create tests. [[5]][5]
 - The requirement of testable code results in a much more complex design
   than might be necessary for the problem at hand. [[5]][5]

Ben's Thoughts
--------------

Pure TDD seems a little too masochistic for most projects. I think that a
hybrid approach that incorporates a reasonable yet thorough amount of
testing might be better. For example, the technique might step you through
these steps.

 1. Think through the design.
 2. Design a suitable API for your problem. This may be done best by writing
    usage examples for your future functional code. This might be related to
    example driven development.

    The design process might involve writing prototypes or even writing some
    functional code (gasp!)
 3. Write thorough tests for the API. Make sure you think through all
    possible inputs and their should-be outputs.
 4. Write the functional code, but don't lean on the tests, use them as an
    aid, but don't turn off your brain.

These steps can be applied at various levels of detail. It should be
possible to write more tests or more functional code at a time. This reduces
the number of context switches that are forced upon the programmer.

TDD feels like everything is oriented around the test, which I don't like.
I would much rather have very nice functional code than very nice tests.
But that's just my personal opinion. I think that the way that the Go and
D programming languages incorporate testing is very useful.

[1]: http://butunclebob.com/ArticleS.UncleBob.TheThreeRulesOfTdd
[2]: http://www.sqlite.org/testing.html
[3]: http://c2.com/cgi/wiki?TestDrivenDevelopment "Test Driven Development"
[4]: http://programmers.stackexchange.com/questions/5560/what-are-the-disadvantages-of-test-first-programming "What are the disadvantages of test-first programming?"
[5]: http://stackoverflow.com/questions/64333/disadvantages-of-test-driven-development "Disadvantages of Test Driven Development"

