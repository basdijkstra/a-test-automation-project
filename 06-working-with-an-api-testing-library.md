# Step 6: Working with an API testing library

In the previous step, we enabled our tests to be run from within a CI pipeline. However, the tests themselves so far haven't been too impressive yet. Time to change that. In this step, we'll add some more tests to our suite, and this time, they'll be tests against an HTTP-based REST API.

Learning how to write tests against APIs is a valuable skill for every tester and developer, and that's why we're covering it in this project as well. In fact, a lot of tests I have seen written (and used to write) against a graphical user interface could and should have been replaced with API tests, as the latter type of tests typically runs faster, requires less maintenance *and* is easier to write, too.

### Adding an API testing library to your project

While you could technically use the HTTP libraries that are built into your programming language, such as the `HttpClient` in `java.net.http` (Java) or the `HttpClient` in `System.Net.Http` (C#), it's probably easier to write your tests using a dedicated API testing library. These libraries will take care of creating HTTP client, sending requests and receiving responses for more, among other things, and leave the actual writing of the tests to you. Here are some examples of popular libraries you might consider:

| Language | API testing library |
| -------- | ---------------------- |
| Java | [REST Assured](https://rest-assured.io) |
| C# | [RestAssured.Net](https://github.com/basdijkstra/rest-assured-net), [RestSharp](https://restsharp.dev), [MSTest](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-mstest) |
| Python | [requests](https://requests.readthedocs.io/en/latest/) |
| JavaScript | [PactumJS](https://pactumjs.github.io), [Axios](https://axios-http.com/docs/intro) |

Most, if not all of these libraries work seamlessly together with the unit testing frameworks [we added to our project earlier](02-working-with-package-managers.md).

### Writing a test for an API - retrieving data

Create a new namespace (C#), package (Java) or folder (Python, JavaScript) and add a new class or module for our API tests.

Your first task is to write a test that performs an HTTP GET to `https://jsonplaceholder.typicode.com/users/1` and checks that:

* the response status code is equal to HTTP 200
* the response `Content-Type` header has a value equal to `application/json; charset=utf-8`
* the response body element `name` has a value equal to `Leanne Graham`
* the response body element `bs` has a value equal to `harness real-time e-markets`

### Writing a test for an API - submitting data

As a next task, let's write a test that submits a new blog post to `https://jsonplaceholder.typicode.com/posts` using an HTTP POST. You can use this hardcoded request body for now:

```json
{
    "userId": 1,
	"title": "My blog post title",
	"body": "This is the text of my latest blog post."
}
```

In a later stage, we'll learn how to create request bodies (and process response bodies) in a more flexible and efficient way.

Also, add a request header `Content-Type` with value `application/json` to your request. Submit the request using HTTP POST and check that:

* the response status code is equal to HTTP 201
* the response body element `id` has a value of type integer

### Making API tests part of our CI pipeline

After you have completed the tests and have checked that they pass when you run them, perform these three tasks:

* Split the step running the tests in your CI pipeline definition into two separate steps: one that runs the tests we wrote in step 3 (our 'unit tests') and another step that runs the API tests we wrote in this step
* Commit and push your changes to the CI definition and the code you wrote in this step to the remote repository and check the CI build output

In the second step, pay special attention to checking whether our tests are now split into two stages. This is a very useful pattern in practice: there's no need to run integration and end-to-end tests if the unit tests fail. Remember: test automation is all about fast feedback!

What you're looking for is a way to tell your test runner to only run tests in a specific folder, namespace or package. The way to do this differs from one test runner to the next. The documentation (or Google) is your friend here.

### That's it!

You have now:

* Selected a tool for API testing and used it to write and run some simple tests against an API
* Made your API tests part of the CI pipeline
* Modularized the build by splitting running the unit tests and running the API tests into separate steps

In the next step, we are going to learn how to use a feature of our test runner that is especially useful when you're writing API tests: we're going to learn [how to write parameterized tests](07-parameterizing-your-tests.md).