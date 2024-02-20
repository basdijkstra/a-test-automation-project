# Working with package managers to add libraries to our project

After we have created a new, empty project, it's time to add the first building block of our test automation solution to it: a unit testing framework.

These frameworks not only help us write and run unit tests more efficiently, but they are also commonly used as test runners for other types of tests, and they are going to be very helpful for all of our tests.

So, that's what we're going to do next: add a unit testing framework to our solution. The most convenient way to do this, and to manage the dependencies of our projects in general, is by using a [package manager](00-setting-up-your-local-development-environment.md#configuring-a-package-manager-for-your-development-environment).

_Note: package managers are frequently also referred to as 'dependency managers'._

### Which unit testing framework do I choose ?

As with pretty much every choice for a specific tool or technique we're making in this project, the answer to this is:

* Go with what your team or company is already using, or
* Pick a popular one that you like or want to learn more about

Here is an incomplete overview of popular unit testing frameworks that you could choose from:

| Language | Unit testing framework |
| -------- | ---------------------- |
| Java | [JUnit](https://junit.org), [TestNG](https://testng.org/) |
| C# | [NUnit](https://nunit.org/), [xUnit.net](https://xunit.net/), [MSTest](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-mstest) |
| Python | [pytest](https://docs.pytest.org/), [unittest](https://docs.python.org/3/library/unittest.html) |
| JavaScript | [Jest](https://jestjs.io/), [Mocha](https://mochajs.org/) |

### How to add a package to my project ?

The way to do this depends on the language you're using and the package manager you're working with.

| Language | How to add a dependency to your project |
| -------- | --------------------------------------- |
| Java | Add the dependency to your project definition file (`pom.xml` for Maven, `build.gradle` for Gradle) |
| C# | Use the NuGet Package Manager in Visual Studio, use `dotnet add package` |
| Python | Use `pip install` |
| JavaScript | Use `npm install` |

### Which version of the package do I need to add to my project ?

Very good question, thank you for asking! Here, too, my recommendations are twofold:

* Use the same version that the rest of your team or company is using, and if that doesn't apply,
* Use the most recent stable version

### That's it!

You have now:

* Added a first package to your new, empty project using a package manager

In the next step, we'll finally get to work writing some code by [adding a first test](03-writing-and-running-a-first-test.md), and we'll use our newly added unit testing framework to do this effectively.