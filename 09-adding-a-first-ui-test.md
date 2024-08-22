# Adding a first UI test

Now that we have learned how to write and run tests against APIs, and how to make them part of your Continuous Integration pipeline, let's move on to another type of tests: the end-to-end, DOM-to-database test against a graphical user interface, also commonly known as the 'UI test'.

From now on, when I talk about a 'UI', I'm referring to the graphical user interface of a web application running in a browser.

While this type of test is very popular, I'm introducing this only now, because it is also the most difficult and most expensive type of test to write, run and maintain. This doesn't mean you shouldn't write and run these tests, but you should definitely be careful when choosing what to automate with this type of test.

### UI automation tools

There are many, many tools out there to help you write your UI tests, ranging from popular open source libraries such as [Selenium](https://www.selenium.dev/), [Cypress](https://www.cypress.io/) and [Playwright](https://playwright.dev/) to a wide range of commercially licensed tools. Most of these tools operate on the [DOM](https://en.wikipedia.org/wiki/Document_Object_Model) of your web application. They allow you to find elements on a web page by querying the DOM, and then perform operations on these elements, such as clicking it, or filling it with text.

Some of these tools, like Selenium, do just that, others, like Playwright and Cypress, are fully fledged frameworks that contain everything you need to write and run your tests and inspect the results.

### Structure of a typical UI test

Most UI tests roughly follow the same sequence of events:

* Open a new browser and start an application
* Perform actions on the application running in the browser
* Verify the result of these actions
* Close the browser to prepare the machine for the next test

Of course, there are many possible variations here - some tests might also involve API calls (good idea!), some tests might perform multiple action-verification iterations (not such a good idea...), but generally speaking, they all contain these steps.

### Identifying elements

To be able to interact with elements on a web page, you will first need to identify them. There are two main ways to do that:

* Using HTML properties of the element
* Using properties of the element visible to human beings

The [locators used by Selenium](https://www.selenium.dev/documentation/webdriver/elements/locators/) are an example of a tool using HTML properties. Other tools identify elements based on image recognition, a clear example of the second option. And then you have locators such as [those used by Playwright](https://playwright.dev/docs/locators) that offer a mix of both.

Getting to know and understand the locator strategies used by your tool of choice is one of the most important things to learn in UI automation, as you'll be using them a _lot_.

### Interacting with elements

After you have identified the element on the page, you should be able to interact with it. Click on a button, fill a textfield with a text value, select a value from a dropdown box, and so on. Your UI automation tool or library will have predefined methods to make this straightforward.

### Verifying element properties

To verify that actions performed in the UI yield the expected result (e.g., performing a login sequence should redirect us to the application home page), we also need to verify properties of elements. Is a specific predefined element visible? Does it contain a certain text value? Here, too, your UI automation tool or library will provide you with methods to make that a straightforward process.

You can then use assertion methods provided either by the UI automation tool itself, or those included in your [test runner](03-writing-and-running-a-first-test.md), to verify that the current state of an element matches your expectations.

### A first UI test

In this step, you're going to write and run your very first UI test. To do that, complete the following steps:

* Add your UI automation library of choice to your project using the dependency manager
* Create a new class that will contain your UI tests
* Create a new test method and give it an appropriate name related to what the test will do
* Write a test that performs the following steps:
    * Open a new instance of Chrome (or your preferred browser)
	* Navigate to https://www.saucedemo.com
	* Locate the username field and fill it with the value 'standard_user'
	* Locate the password field and fill it with the value 'secret_sauce'
	* Locate the 'Login' button and click it
	* Verify that a link with the text 'Sauce Labs Backpack' is visible
	* Close the browser

Run your test to see if it passes.

### That's it!

You have now:

* Written and executed your very first UI test

You might have noticed that it was a bit more work compared to the unit and API tests we wrote in the previous steps. That's exactly what I was talking about when I said that this type of tests is the hardest to write! And there's much more to explore and learn about UI tests.

In the next step, we are going to learn how to [run these tests as part of our CI pipeline](09-running-our-ui-tests-in-ci.md). This takes a little more effort than it took us to run unit and API tests in CI, and that's why I'm dedicating an entire step to the subject.