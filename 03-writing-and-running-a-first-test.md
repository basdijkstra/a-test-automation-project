# Writing and running a first test

Now that we've set up our development environment, created a new project and added a unit testing framework, it's time to start writing code: our first tests.

In this step, we shouldn't be too concerned about the purpose and the complexity of the test yet, as the goal of this step is to get some experience with the process of writing and running tests. That's why we're going to create some of the most simple and straightforward tests possible: tests for the arithmetic capabilities of the programming language we're using. It probably doesn't get much more straightforward than that.

### Creating a test class or module

Like any code, your test code should be placed inside a class (for class-based languages like Java or C#) or a module (for other languages). So, that's the first thing we'll need to doo: adding a test class or method to your project. Some languages and some frameworks require that class or module to:

* be in a folder with a specific name or location, and/or
* follow specific naming conventions

As an example, for a Maven-based Java project, test classes should:

* be placed in the `src/test/java` folder of your project, and
* follow one of several naming conventions, I prefer to use `*Test.java`, e.g., tests for a calculator go in `CalculatorTest.java`

Be sure to check if there are any naming conventions for the programming language and unit testing framework you're using, otherwise the outcome might be that your tests will not be discovered and run.

### Creating a test method

In most testing frameworks, a test is 'just' a regular method with some unique properties that identify it as being a test method. Examples include:

| Framework | How tests are identified |
| --------- | ------------------------ |
| JUnit (Java) | Methods with a `@Test` attribute |
| NUnit (C#) | Methods with a `[Test]` annotation in a class with the `[TestFixture]` annotation |
| pytest (Python) | Methods with a name starting with `test` |
| Jest (JavaScript) | Code inside a `test()` block |

Write two test methods and come up with good names for them:

* In the first test, we'll add 2 and 2 and expect the outcome to equal 4 - this test will pass
* In the second test, we'll add 3 and 5 and expect the outcome to equal 7 - this test will fail

Naming things in programming is an art, and if you're looking for some inspiration, [here's an article you might want to read](https://dzone.com/articles/7-popular-unit-test-naming).

### Adding the implementation of the test and its assertions

TO BE CONTINUED