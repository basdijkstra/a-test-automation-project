# Running our UI tests in a Continuous Integration pipeline

In the previous step, we created our first UI test running against a browser, and we made it work locally. Now, we also want to make it work in a Continuous Integration pipeline. This requires a little more work and background information compared to the unit and API tests we added to our pipeline earlier, which is why I'm dedicating a separate step to this topic.

### Browsers, browsers

The added complexity of running UI tests in a pipeline is mostly caused the fact that you'll need browsers installed on or available to the machine you're running your tests on. Generally speaking, there are three different ways to address this challenge.

#### Make sure that the machine you're running your tests on has the browsers installed

Most CI platforms give you the option to use pre-built images to run your tests on, and many of these images have browsers pre-installed. As an example, [here is the list of pre-built images available for GitHub Actions](https://github.com/actions/runner-images?tab=readme-ov-file#available-images). If you look at the list of tools installed in a typical `ubuntu-latest` image, you'll see that it comes with Chrome, Edge and Firefox pre-installed, for example.

#### Use a tool that brings its own browsers

This is most notably the case with [Playwright](https://playwright.dev/). When you add Playwright to your project, you can also install (customized versions of) popular browsers that can be used for test execution. One thing to keep in mind with Playwright specifically is that a specific Playwright version is linked to specific browser versions, so if you want to test against the latest version of a browser, you should make sure you also use the latest version of Playwright.

#### Use a SaaS solution that manages the browsers for you

There are many platforms available these days that make selecting specific browsers, browser versions and operating systems to run your tests on a breeze. Well-known examples of such platforms are [SauceLabs](https://saucelabs.com/) and [BrowserStack](https://www.browserstack.com/). Of course, using these services comes at a price.

### Headless test execution

Another thing to keep in mind when you run your UI tests on a machine in CI is that you will likely need to run your tests in headless mode, because most of the time, these machines do not have display hardware. An additional benefit of running tests in headless mode is that they typically run slightly faster this way.

Some tools, such as Playwright and Cypress run tests in headless mode by default, other tools, like Selenium, do not. All of these tools give you the ability to switch headless mode on and off depending on what your requirements or preferences are.

### Adding your UI tests to a CI pipeline

The above information should give you enough background to get started adding the UI tests we created in the previous step to our CI pipeline. Make sure to run these tests in their own stage, too, after the unit and API tests have finished.

### That's it!

You have now:

* Learned what it takes to run UI tests in a Continuous Integration pipeline
* Added your UI tests to a separate stage in that same pipeline

In the next step, we'll look at some techniques that we can apply to make our test execution more robust by means of proper waiting and synchronization.