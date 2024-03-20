# Step 3: Writing and running a first test

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

Now that we've created the test methods, let's implement their bodies. The first test should execute these steps:

* Add the integers 2 and 2 and store the result in a variable
* Assert that the value of that variable is equal to 4

The second step should be performed using a suitable assertion method provided by the unit testing framework you're using. These assertion methods determine the result of our tests. The test passes when the assertions pass (and the code does not throw exceptions), otherwise the test fails.

The second test should execute very similar steps:

* Add the integers 3 and 5 and store the result in a variable
* Assert that the value of that variable is equal to 7

This assertion will obviously fail, as 3 and 5 is 8, not 7, but that's exactly the point.

### Running our tests from within our IDE

Now that we have written our tests, let's run them. Most IDEs have some way of running individual tests or groups of tests. IntelliJ, WebStorm, PyCharm etc. provide little green triangles/arrows next to the testing methods to run them, Visual Studio has a Test Explorer window, etc.

Run your tests and observe the result. One of our tests should pass, while the other should fail. Inspect the result and the feedback returned by your unit testing framework.

As we move along, it becomes increasingly important that you can quickly see which of your tests pass, and which of them fail and for what reason, so best to get started practicing that right away.

### Running our tests from the command line

After running our tests from within our IDE, we're moving on to running our tests from the command line. Why? Because that's how tests are run from within a Continuous Integration pipeline, and as we will start building such a pipeline very soon, it is important to learn this right now.

The way you run tests from the command line depends (of course) on the programming language and the unit testing framework you're using. And when you're using Java, you'll probably want to use Maven or Gradle to run your tests, meaning that you might want to look into how to do that.

Here are some example command to run tests in different languages and frameworks:

| Language and framework | Running tests from the command line |
| --------- | ------------------------ |
| Java and Maven | `mvn test` |
| C# (all frameworks | `dotnet test` |
| Python and pytest | `pytest <name_of_test_module>` |
| JavaScript and Jest | `jest`, but the recommended way is to add this as a script in `package.json` and run `npm test` |

Again, inspect the output provided on the command line interface and see if you understand what is happening. The test results should be the same: 2 tests executed, 1 pass, 1 failure.

### That's it!

You have now:

* Created a new test class or module
* Adding both a passing and a failing test to that class or module, including assertions
* Learned how to run these tests from within your IDE
* Learned how to run these tests from the command line

In the next step, we are going to make sure we don't lose our work and enable others to use and contribute to our code by [putting it under version control](04-bring-our-code-under-version-control.md).