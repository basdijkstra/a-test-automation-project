# Running our tests as part of a CI pipeline

In the previous step, we have brought our test code under version control, allowing other developers and automation engineers to contribute to the code we wrote. The next step is to make sure that our tests are run for every new change that is made to the code base, and the most efficient way to do that is to automate the process of running our tests and reporting on the results. Typically, this is done through defining a Continuous Integration (CI) pipeline that takes care of this for us.

There are many CI platforms out there, and I'm not going to dictate which one you should choose. The same rules apply here that apply to language and tool selection in previous steps:

* Choose the CI platform that is used in your team / your company, or if that doesn't apply
* Choose the one closest to where you stored your code

What I mean when I say 'the one closest to where you stored your code'?. Choose the one that causes the least amount of friction regarding automation and access control. If you brought your tests under version control on GitHub, [GitHub Actions](https://github.com/features/actions) is a 'plug and play' choice for CI, as there's no configuration needed to allow the pipeline you define to access the code. The same goes for using [Azure DevOps](https://azure.microsoft.com/en-us/products/devops) for version control, for example: in that case, it's wise to also define your pipeline in Azure DevOps.

### Defining our pipeline

Most CI platforms these days allow you to define your pipeline in code, as part of your (test) code base. Defining your pipeline is a three-step process:

* Define a `.yaml` file containing the pipeline instructions in the right location in your code base
* Add the required steps to setup the execution schedule, required infrastructure, checkout the code, install the dependencies and run the tests in the `.yaml` file
* Push the code, including the pipeline definition, to your remote repository

If you completed these three steps successfully, the CI platform will take care of the rest.

### Pipeline steps

As mentioned in the previous section, a minimal pipeline definition contains a number of components we need:

* A schedule, defining when the tests should be run. This could be an activity-based trigger (i.e., on every commit or completed pull request), or a time-based trigger (e.g., every morning at 6 AM).
* The infrastructure (the virtual machine) that the tests need to run on. Your code needs a machine to run on, and you should tell your CI what that machine should look like.
* A step to checkout the code from version control
* A step to install the dependencies that are required to run your tests
* A step to run the tests and report on the results

For now, I would recommend to at least run your tests every time new code is pushed to the remote repository. This ensures that your tests are run on a regular basis.

For inspiration, here's a link to the pipeline definition for one of the reference implementations, this one based on C# and NUnit and using GitHub Actions as the CI platform (LINK TO FOLLOW).

### Is that all?

Well, yes and no. There's more, much more to learn about CI systems in general. That's outside the scope of this project, though. If you want to learn more about GitHub Actions, [here's a great, free video course](https://testautomationu.applitools.com/github-actions-for-testing/) specifically geared towards building test execution pipelines.

### That's it!

You have now:

* Defined a Continuous Integration pipeline 'as code'
* Added Continuous Integration to your test project to ensure that your tests are run on a regular basis

In the next step, we are going to add a second type of tests to our project: tests against an HTTP-based API [using a dedicated API testing library](06-working-with-an-api-testing-library.md).