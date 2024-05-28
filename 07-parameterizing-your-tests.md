# Parameterizing our tests

In the previous step, we added a new type of tests to our project: tests for an HTTP-based API. We selected a tool for API testing and used it to write and run some simple tests against an API, we made those API tests part of the CI pipeline, and we modularized the build by splitting running the unit tests and running the API tests into separate steps.

In this step, we'll write some more API tests and get introduced to a concept that is often used in API testing, the concept of parameterized tests.

### What are parameterized tests?

APIs are all about data: retrieving data from a provider, sending data to a provider for processing, or updating or deleting pre-existing data. APIs also often expose some kind of backend business logic, for example to a frontend. To properly test this logic, you'll often want to write and run multiple test cases for that logic. For example, if you want to test the addition operation for a calculator API, you probably want to run multiple test cases, such as:

* Does adding 1 and 1 yield a result of 2?
* Does adding 0 and 0 yield 0?
* Does adding -1 and 1 yield 0?
* Does adding –2147483648 and 2147483647 yield -1?

and so on.

In cases like this, instead of having multiple tests that essentially exercise the same piece of logic, just with different combinations of input and expected output data, it's recommended to use a parameterized test instead. This has a number of advantages, including:

* Less code duplication
* Editing existing or adding new test cases is often a matter of editing or adding the data
* It's immediately clear when reading the code that the test cases exercise the same logic

When you run the parameterized test, your test runner will 'expand' (for lack of a better word) that parameterized test again and interpret it as a separate test for each test case, meaning that if you have 4 examples / test cases, it will run 4 tests, and since all of them are isolated from the others, if test 2 fails, test 3 and 4 will still be executed just as when you would have included them as separate test methods.

Are there any situations where parameterized tests are not a good idea? Yes, of course, especially in the case of full-stack tests through the graphical user interface. In other words, [don't repeat your paths](https://chrismcmahonsblog.blogspot.com/2017/11/ui-test-heuristic-dont-repeat-your-paths.html).

### Creating parameterized tests

All modern test runners / unit testing frameworks support the creation and execution of parameterized tests in one way or another. Here are some examples:

| Framework | Write parameterized tests using |
| --------- | ------------------------ |
| JUnit (Java) | The `@ParameterizedTest` annotation ([docs](https://junit.org/junit5/docs/current/user-guide/#writing-tests-parameterized-tests)) |
| NUnit (C#) | The `[TestCase]` ([docs](https://docs.nunit.org/articles/nunit/writing-tests/attributes/testcase.html)) or the `[TestCaseSource]` attribute ([docs](https://docs.nunit.org/articles/nunit/writing-tests/attributes/testcasesource.html)) |
| pytest (Python) | The `@pytest.mark.parametrize` marker ([docs](https://docs.pytest.org/en/latest/how-to/parametrize.html)) |
| Jest (JavaScript) | The `test.each` construct ([docs](https://jestjs.io/docs/api#testeachtablename-fn-timeout)) |

Using the test runner you've used so far, extend the coverage of the first API test by converting it into a parameterized test that GETs data for users with IDs `1`, `2` and `3` and verifies the following things:

| User ID | HTTP status code | Response `Content-Type` header | Response body element `name` | Response body element `bs` |
| ------- | ---------------- | ------------------------------ | ---------------------------- | -------------------------- |
| `1` | 200 | `application/json; charset=utf-8` | `Leanne Graham` | `harness real-time e-markets` |
| `2` | 200 | `application/json; charset=utf-8` | `Ervin Howell` | `synergize scalable supply-chains` |
| `3` | 200 | `application/json; charset=utf-8` | `Clementine Bauch` | `e-enable strategic applications` |

Think about which values should be parameterized, and which ones can remain constant / hard-coded.

### Adding parameterized tests to our pipeline

After the work we've done in the previous step, this one should be a breeze. Make sure, though, that these tests are part of the API testing stage in your pipeline definition.

### That's it!

You have now:

* Added a parameterized API test to your suite of tests
* Made your parameterized API tests part of the CI pipeline

In the next step, we are going to learn how to use another feature that is very useful when you're writing API tests: we're going to learn [how to serialize objects to JSON request payloads](08-serializing-objects-to-json.md).