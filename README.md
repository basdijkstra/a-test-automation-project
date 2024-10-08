# A test automation project

There is a lot of good content out there on how to build tests with different tools. However, what's often lacking is the opportunity to put what you have read, seen or heard into practice.

That deliberate practice, though, is essential when you really want to learn a new skill. Reading, watching or listening alone isn't going to get you there (ever tried to learn swimming just by watching other people swim?).

This is the reason I published this project. It will give you an opportunity to get your hands dirty on a test automation challenge, covering several different tools and technologies that a test automation engineer encounters when they work on real-life projects.

By going through this project step by step, you will build a solution that serves as a portfolio project for your current or prospective employer.

This project is an ongoing piece of work, meaning that updates and new challenges will be added over time.

### What am I going to learn?

This project covers:

* Step 0: [Setting up your local development environment](00-setting-up-your-local-development-environment.md)
* Step 1: [Creating a new empty project](01-creating-a-new-empty-project.md)
* Step 2: [Working with package managers to add libraries to our project](02-working-with-package-managers.md)
* Step 3: [Writing and running a first test](03-writing-and-running-a-first-test.md)
* Step 4: [Working with Git and GitHub to bring our code under version control](04-bring-our-code-under-version-control.md)
* Step 5: [Running our tests as part of a CI pipeline](05-running-our-tests-in-a-ci-pipeline.md)
* Step 6: [Working with an API testing library](06-working-with-an-api-testing-library.md)
* Step 7: [Parameterizing your tests](07-parameterizing-your-tests.md)
* Step 8: [Serializing objects to JSON](08-serializing-objects-to-json.md)
* Step 9: [Adding a first UI test](09-adding-a-first-ui-test.md)
* Step 10: [Running our UI tests in CI](10-running-our-ui-tests-in-ci.md)
* Step 11: [Working with waiting and synchronization strategies](11-waiting-and-synchronization-techniques.md)
* Step 12: [Separating the 'what' from the 'how' in our UI tests](12-separating-the-what-from-the-how.md)
* Step 13: [Further improvements for our code](13-further-improvements-for-our-code.md)

### How is the workshop material presented?

This project will *not* hold your hand through every step. I will not provide you with instructions that tell you exactly what to do and what to type where. The point of this project is to figure things out and build things _yourself_.

I will, however, make sure that there is a logical progression from one step to the next, and I will provide information on the 'why?' and 'what?' (but again, not the 'how?') for every step. Links to relevant learning material will be included where applicable, for your review.

If you're really stuck, by all means have a look at one of the reference implementations for inspiration. The goal, though, is to build a solution yourself. Getting stuck, trying to find out how things work and the frustration that comes with this *is part of the learning process*.

### What tools can I use for this project?

That's up to you. I deliberately set up this project to be tool- and programming language-agnostic. So, whether you want to use Java, C#, Python, JavaScript with your libraries and test frameworks of choice, or if you want to use low-code tools like [Robot Framework](https://robotframework.org/), it's up to you.

I will provide reference implementations for some of the most popular languages, tools and libraries, and I am happy to include yours, too.

### What if I'm stuck?

Are you stuck? Awesome! That's how you know you're learning something new. Here are some tips to help you get unstuck:

* Ask an experienced coworker for help
* Pair up with a fellow learner
* Ask Google / ChatGPT / StackOverflow / ...

If you're really, really stuck and still can't find an answer, please [open an issue](https://github.com/basdijkstra/a-test-automation-project/issues) on this repository and I (or maybe someone else) will gladly have a look at it.

### How can I get my work reviewed?

Here are some ideas to get feedback on your code:

* Pair program with a fellow learner while working on the exercises
* Ask an experienced coworker to have a look at your code

Unfortunately, I don't have the capacity to give detailed feedback to individuals on their code myself.

### Reference implementations

| Link | Language | Test runner | API library | UI library | CI platform |
| ---- | -------- | ----------- | ----------- | ---------- | ----------- |
| [Click](https://github.com/basdijkstra/atap-csharp-nunit-restassurednet-playwright) | C# | NUnit | RestAssured.Net | Playwright | GitHub Actions |

### Can I contribute to this project?

Absolutely! There are several ways to do this:

* Provide a reference implementation for the project
* Submit a pull request containing improvements or additions to the workshop material
* Spread the word about this project at your company, on social media, or any other place

### Is this workshop available as an in-house project for my organization?

I am more than happy to discuss options to bring this project to your organization. We can then tailor the content to your specific requirements, and we can perform the exercises _in your context, using your technology stack and applications_. Send me an email at bas[AT]ontestautomation[DOT]com for more details.