# Waiting and synchronization techniques

One of the biggest reasons for UI tests to fail, either intermittently ('flaky tests') or every time, is a lack of proper waiting and synchronization built into your tests.

When I say 'waiting and synchronization', I mean waiting for elements that you want to interact with on the screen to be in the right state before you perform the desired interaction. Examples of this are:

* Waiting for a button to become visible and enabled before you click on it
* Waiting for a text field to become visible and enabled before you type text into it
* Waiting for a text label to contain a certain text before you verify it

and so on.

Now, in my experience, this is one of the hardest things to 'get right' in test automation (together with managing test data), and it has become more difficult with the rise of modern web UI frameworks like Angular and React, where a lot of client-side rendering and JavaScript processing is happening inside the browser. This makes waiting and synchronization one of the most important things you should learn on your journey to become more proficient in automation.

### The good news...

The good news is: most, if not all tools these days offer help in waiting and synchronization. Often, this is implemented in the form of a polling mechanism that periodically polls the UI (or in the case of web applications, the DOM) to check if a specified element is in the desired state.

| Tool | Polling / waiting mechanisms |
| ---- | ---------------------------- |
| Selenium WebDriver | [Implicit or explicit waits, to be implemented by the user](https://www.selenium.dev/documentation/webdriver/waits/) |
| Playwright | [Predefined waiting strategies, can be used out of the box](https://playwright.dev/docs/actionability) |
| Cypress | [Predefined waiting strategies, can be used out of the box](https://docs.cypress.io/guides/core-concepts/interacting-with-elements#Actionability) |

No matter if you need to implement the waiting yourself (e.g., Selenium) or if it is largely taken care of for you (e.g., Playwright, Cypress), you need to understand how your tool deals with waiting and synchronization if you want to understand what exactly happens when your test fails because it doesn't seem to find an element, or when an interaction with that element fails.

Oh, and if you use Selenium, I would recommend implementing explicit waits, as these will give you much more flexibility when it comes to defining what it is exactly that you're waiting for.

### Improving the stability of your tests

In this step, I'm going to ask you to improve the stability and reliability of your UI tests by properly implementing waiting techniques.

If you used Cypress or Playwright, and your tests ran fine so far, that's great. Take some time to better understand what these frameworks do for you in terms of waiting and synchronization.

If you used Selenium WebDriver or a library that's based on it, add explicit waits before each element interaction to make sure that the element is in the right state before you interact with it. If you find yourself repeating the code a lot, extract this logic into a helper method. [Here](https://www.ontestautomation.com/using-wrapper-methods-for-better-error-handling-in-selenium/) is an old blog post of mine with an example, and [here](https://www.ontestautomation.com/on-no-longer-wanting-to-depend-on-expectedconditions-in-my-c-selenium-webdriver-tests/) is a newer one specifically for Selenium in C# that also explains why you shouldn't rely on ExpectedConditions in those bindings.

What I DON'T want to see in your test code anymore after this step is `Thread.Sleep()` statements (or the equivalent of that for your language)! If you implemented your waiting properly, you shouldn't have to rely on them anymore.

### That's it!

You have now:

* Learned more about waiting and synchronization in popular test libraries and frameworks
* Made your test execution more stable and reliable by implementing waiting and synchronization techniques in your tests

In the next step, we'll further improve the readability and maintainability of our tests by [separating the 'what' from the 'how'](12-separating-the-what-from-the-how.md), using a popular UI automation pattern called Page Objects.