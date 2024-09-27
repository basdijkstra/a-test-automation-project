# Further improvements for our code

We have come a long way by now, and I hope you enjoyed working on this project.

But are we done now? Well, yes and no. In the steps up to now, you have learned more about what I think are the most fundamental tools and techniques to learn as a test automation engineer:

* Starting a project from zero
* Working with package managers and build tools
* Working with unit, API and UI testing libraries
* Working with version control systems and CI orchestrators

That's a lot, but it's not all. There is much left to explore to further grow your expertise.

### Improving reporting of our test results

We haven't paid a lot of attention to reporting yet, but people do love a good report summarizing the results of their test runs. There are several different types of reports to explore, including:

* Generating HTML reports using frameworks like [Allure](https://allurereport.org/) or [ExtentReports](https://extentreports.com/)
* Improving the reporting in your CI pipeline with custom steps. [This is an example for GitHub Actions](https://github.com/marketplace/actions/test-reporter)
* Publishing notifications via email, Slack or other communication channels

### Working with libraries that support BDD

When your team is practicing Behaviour-Driven Development (BDD), tools like [Cucumber](https://cucumber.io/), [Reqnroll](https://reqnroll.net/) and [Behave](https://behave.readthedocs.io/en/latest/) are very useful for turning specifications into automated acceptance tests.

Knowing a thing or two about both BDD as a practice and tools like the ones I mentioned is useful knowledge to have as a test automation engineer.

Beware, though, of falling into the trap of sticking a Cucumber / Reqnroll / Behave layer on top of your tests if your team isn't actually practicing BDD. In other words, if you are the only one reading and contributing to the Given-When-Then specs that are commonly used by these tools, [it's probably not worth the effort](https://www.ontestautomation.com/to-bdd-or-not-to-bdd/).

### Looking into other types of testing

The tests we wrote so far have focused on what people like to call 'functional testing' ([I'm not a big fan of that description myself](https://www.ontestautomation.com/lets-talk-about-behaviour-instead/)), but of course there is much more to learn. Performance, security and accessibility testing are the first things that come to mind.

These types of testing are beyond the scope of this project, but resources like [Test Automation University](https://testautomationu.applitools.com/) and [APIsec University](https://www.apisecuniversity.com/) are great starting points for learning more.

Finally, I would like to congratulate you on your hard work and on completing this project!

Feel free to share your experience by writing a post on social media, or by sending me an email at basATontestautomationDOTcom. If you have something to add or if you want to report an issue, please use [GitHub](https://github.com/basdijkstra/a-test-automation-project/issues) to do so.

Cheers!