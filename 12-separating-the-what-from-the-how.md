# Separating the 'what' from the 'how' in our UI tests

So, right now we have our first working UI test(s), running both locally and in our Continuous Integration pipeline. That's a great achievement, well done! However, if you're anything like past me, your test will probably be written still in a very procedural way. Click here. Type 'ABC' there. Wait for label to become visible.

While your test might work fine that way, especially now that we've added proper waiting and synchronization in the previous step, there are a couple of problems with these procedural type-here-click-there tests:

* Tests written in this style are very hard to read, especially when they involve a lot of element interactions
* There will be a lot of repetition in the code once the number of tests grows
* Whenever the GUI changes (which typically happens frequently), many tests will have to be updated, and the aforementioned repetition causes a high maintenance burden

So, what to do to resolve this?

### One potential answer

One way to address the problems above is by separating the 'what' from the 'how' in our UI tests. This means creation an abstraction layer that separates the test flow ('what are we trying to do in our test?') from the technical implementation ('how is our tool interacting with UI elements to perform specific actions?').

There are several ways to create this abstraction layer, and one of the most popular approaches is the Page Object pattern. More background information on that pattern [here](https://martinfowler.com/bliki/PageObject.html) and [here](https://www.selenium.dev/documentation/test_practices/encouraged/page_object_models/).

This is not the only way to achieve a separation between 'what' and 'how', by the way. Alternatives such as the [Screenplay pattern](https://serenity-js.org/handbook/design/screenplay-pattern/) have been created to address the same issue, using a different approach. In the end, these techniques are all about creating a layer of abstraction that separates test behaviour (what) from test and application implementation (how).

Oh, and by the way, these patterns are not unique to test automation, but simply an application of [encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)), one of the four fundamental principles of object-oriented programming.

Now, there are many different ways of writing Page Objects. Some are better than others, especially for specific contexts, but none of them is 'the best' (this is a general truth in test automation, software development and life in general by the way, but I digress).

### Adding Page Objects to your tests

As a first step to using the Page Object model to make your tests easier to read, write and maintain, follow these steps:

* Create a new class that represents the login page for the https://www.saucedemo.com demo application
* Add a constructor that creates a new instance of the page object, and pass in the required browser or driver object
* Create properties for the elements on the page (username and password textfields, login button)
* Create a method that performs the login action as a sequence of element interactions
* Parameterize the login method by allowing you to pass in the username and password as arguments
* Finally, replace the element interactions in the test with the instantiation of the login page class and call the login method

Completing these steps will hopefully show you that separating the 'what' from the 'how' makes your test easier to read and write.

Now, go ahead and repeat these steps for the other pages in the application. When you're done, your test method should no longer contain any references to element locators or waiting and synchronization techniques. These are all moved to the page object classes.

### That's it!

You have now:

* Learned more about the Page Object pattern and how to use it to separate the 'what' from the 'how' in your tests
* Greatly improved the readability and maintainability of your tests by applying the encapsulation principle of object-oriented programming

In the next step, we will look at a number of [further improvements](13-further-improvements-for-our-code.md) that we can make to our code to make it even more robust and easier to read and write.