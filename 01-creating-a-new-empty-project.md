# Creating a new, empty project

Before we can start writing code, we need to set up a project first. There are many different ways to do this, and the ways to do this also differ from one language and tool set to the next.

Some common ways to create a new project are:

* Using your IDE - Most IDEs include wizards that allow you to create a new project using different presets and templates
* Using Command Line Interface tools - Most languages offer command line tools to quickly create a new project and do the heavy lifting for you

Within the scope of this project, let's create as bare-bones a project as we can. That means we need to do some additional work before we can start writing our tests, but it also means we get the opportunity to learn a little more about how projects and dependencies work. More about that [in the next step](02-working-with-dependency-managers.md).

Here are some examples of different ways to create a new project for different languages:

| Language | From the IDE | Using the CLI |
| -------- | ------------ | ------------- |
| C# | [Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/create-new-project) (choose 'Class Library') | [dotnet new](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new) |
| Java | [IntelliJ](https://www.jetbrains.com/help/idea/new-project-wizard.html) | [Maven archetypes](https://maven.apache.org/archetypes/maven-archetype-simple/) |
| Python | [PyCharm](https://www.jetbrains.com/help/pycharm/creating-empty-project.html) | Create a folder, that's all, maybe consider [a virtual environment](https://docs.python.org/3/library/venv.html) |
| JavaScript / NodeJS | [WebStorm](https://www.jetbrains.com/help/webstorm/creating-projects-in-product.html) | [npm init](https://docs.npmjs.com/cli/v10/commands/npm-init) |

There are many other ways to create a new project, but the ones listed here should have you covered in most cases.

### Location, location, location

An important thing to consider when you create a new location is where to store it on your file system. I prefer to have a single top-level folder that contains all my projects, no matter what the language or tool set used it. As I'm a Windows user, for me that's `C:\Git`.

Feel free to choose a location of your own and organize your work the way you want to, as long as you make it easy for yourself to find and access your projects later on.

### Naming

A project is stored in a folder structure containing all the subfolders and files that are part of the project. In most cases, the top-level folder and all necessary subfolders will be created for you when you create a new project (but sometimes they won't). In any case, it's a good idea to use a short, descriptive name for your top-level project folder.

I myself like to use kebab-casing (i.e., all lowercase characters, words separated by hyphens), because that's the most common format for GitHub repository names, and I like my Git repository to have the same name as my top-level project folder for traceability. Again, please follow the standards your company uses, or if they don't (even though they should!) pick something you're comfortable with.

### That's it!

You have now:

* Created a new project that is going to contain your test code
* Placed the project in a location on your file system where you can easily find it
* Renamed the top-level project folder to give it a short but descriptive name

In the next step, we'll [use dependency managers](02-working-with-dependency-managers.md) to add libraries to our project that we're going to need to write our tests.