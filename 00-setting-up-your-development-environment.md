# Setting up your development environment

Test automation is software development. That means that before you can even start to think about writing and running tests, you'll need to set up a development environment on your machine. This includes completing several steps.

### Setting up the Software Development Kit (SDK) for your language of choice

To be able to write and execute code, you'll need an SDK for the language of your choice. So, if you haven't decided on what language you are going to use for the project, this is the moment to do just that.

For most programming languages, setting up the SDK is fairly straightforward. You download the binaries, run an installer or perform the necessary installation instructions, and you should be good to go.

Here are links to official SDK download sites for some of the most popular programming languages:

* [Java](https://www.oracle.com/java/technologies/downloads/)
* [C#](https://dotnet.microsoft.com/en-us/download)
* [Python](https://www.python.org/downloads/)
* [JavaScript (Node.JS)](https://nodejs.org/en/download)

#### What version of the SDK do I need?

Well, it depends :) The first and best choice is to ask around in your team or organization to check what version they are using. Then choose that.

If you don't get an answer to that question, your safest bet is to choose the latest [LTS (Long-term Support) version](https://en.wikipedia.org/wiki/Long-term_support) for your language.

#### How do I know if the SDK installation was successful?

Test it! Open a new command prompt or terminal and run the command that displays the currently active version of your SDK.

* [Java] `java -version`
* [C#] `dotnet --version`
* [Python] `python -version`
* [JavaScript(Node.JS)] `node -v`

If that displays the version of the SDK you just installed, you're good to go. If not, fix the problem until it does.

### Configuring a package manager for your development environment

We are not going to write _all_ the code required for our test automation project ourselves. Rather, we will make use of common open-source libraries and tools that were written by other developers for us to use.

To be able to do this, you'll need to configure a tool that can take care of managing these packages for you: the package manager (it's all in the name!).

Most languages include the default package manager with their SDKs. C# / .NET has [NuGet](https://www.nuget.org/), Python has [pip](https://pip.pypa.io/en/stable/) and JavaScript / Node.JS has [npm](https://www.npmjs.com/). If you use any of these languages, you're good to go.

If you're using Java, there's good and bad news. The good news is: you've got a choice between [Maven](https://maven.apache.org/) and [Gradle](https://gradle.org/). Both are fine. The bad news is: you need to install and configure those yourself. So do that now, please.

### Setting up an IDE

Technically, you can write all your code in Notepad++ or a similar plain text editor. To be an efficient and productive test automation engineer / developer, you'll probably want to use an Integrated Development Environment (IDE). It's basically a text editor for your code on steroids.

There are many, many good IDEs out there, and I am _not_ going to tell you which one to use. Pick what the rest of your team uses, pick what you're comfortable with.

Here are some examples of good IDEs:

* Java: [IntelliJ](https://www.jetbrains.com/idea/), [Eclipse](https://www.eclipse.org/ide/)
* C#: [Visual Studio](https://visualstudio.microsoft.com/vs/)
* Python: [PyCharm](https://www.jetbrains.com/pycharm/)
* JavaScript: [WebStorm](https://www.jetbrains.com/pycharm/)

And then there's also [Visual Studio Code](https://code.visualstudio.com/), which is a very good multi-purpose IDE, which means you can use it for every language (given that you install the corresponding plugins).

### Version control with Git

Version control plays a major part in software development, and guess what test automation is also software development so you gonna need Git. Many Git GUI clients have Git build in, but you can also choose to use Git via commands. 

Git GUI Client
* [SourceTree](https://www.sourcetreeapp.com/)

Git via Command line
* [Git-scm](https://git-scm.com/)

Please note that many development teams have unwritten rules regarding branching and pushing, ask a developer what the team rules are.

### That's it!

You have now:

* Set up a Software Development Kit for your language of choice
* Set up the package manager to help you manage tools and libraries for your project
* Set up an IDE to help you write and run code efficiently

Onwards to the next step, where we'll [create a new, empty project](01-creating-a-new-empty-project.md) that is going to contain our tests.