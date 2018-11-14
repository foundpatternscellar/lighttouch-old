<p align="center"><img width="100" src="https://i.imgur.com/zwjfmrF.png" alt="lighttouch logo"></p>

<p align="center">
  <a href="https://github.com/foundpatterns/lighttouch/releases"><img src="https://img.shields.io/badge/version-0.9.9-blue.svg" alt="Versioning"></a>
  <a href="https://github.com/foundpatterns?q=&type=fork&language=lua"><img src="https://requires.io/static/3.5/badges/flat/up-to-date.svg" alt="High-Quality Joke"></a>
  <a href="https://github.com/foundpatterns/lighttouch/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=" alt="Contributions Welcome"></a>
  <a href="https://discord.gg/sWCQxT"><img src="https://img.shields.io/badge/chat-on%20discord-7289da.svg" alt="Chat"></a>
</p>

Lighttouch is a framework that makes complex application development simpler.  It does this through broad use of [component-oriented design](https://en.wikipedia.org/wiki/Component-based_software_engineering) intended to offer programmers a well-researched alternative to starting with a blank canvas - "put your code anywhere".  [Code organized](https://en.wikipedia.org/wiki/Structured_programming) this way raises the limits of implementation reusability and cross-pollenation of diverse applications.  Without this applications tend to get walled into handling only a single use case or grow while having trouble from too many layers of abstraction. 

### Lighttouch Packages

Packages are the main unit of addon functionality. They leverage [event-driven](https://en.wikipedia.org/wiki/Event-driven_programming), [rule-based](https://en.wikipedia.org/wiki/Rule-based_system) programming.  This means packages consist of actions, events, and rules.  Events are like [hooks](https://stackoverflow.com/questions/467557/what-is-meant-by-the-term-hook-in-programming) where additional logic can run.  Rules check a conditional statement of any complexity and trigger events.  When an event triggers, its actions run in weight order.  Actions are the individual mechanisms of additional functionality that have a distilled purpose and can run on any associated event.

80% of this functionality builds on top of [Luvent: A Simple Event Library for Lua](https://github.com/ejmr/Luvent).  You could probably get away with the summary below of Lighttouch's use, but it's still worth checking out.  It has a great Readme.  The basic difference between what Luvent does and what Lighttouch does is that while writing a Lighttouch app, you put that functionality into individual files, and Lighttouch sets everything up for you.

Events are very simple.  They get loaded into a global list by reading each package's `events.txt` file.  They can be disabled in a `disabled_events.txt` file.  Potential improvements include a simpler interface and ordering execution by weight.

Rules are basically an `IF` statement with some metadata.  If the configured conditions, specified in the body of a rule as Lua code are `TRUE`, then the specified events will trigger and the objects specified in the input parameters will get passed to the attached actions.

Actions are individual, dynamic functions that can run where they are needed.  You simply code what you want to do, and leave the parts about when it will run and in what order to the other logic connected through the yaml header.  Actions should not have conditions in them.

### Core Modules

Lighttouch also provides modules for content management (thus far, targeting file-based, document-oriented databases), robust logging for web applications, syntax sugar, and more.  These core modules + loaders mentioned for packages + and init script make up [Lighttouch Base](https://github.com/foundpatterns/lighttouch-base).

### Installation

Lightouch has 3 dependencies:
* **[git](https://git-scm.com)** [version control manager](https://en.wikipedia.org/wiki/Version_control)
* **[peru](https://github.com/buildinspace/peru)** [package manager](https://en.wikipedia.org/wiki/Package_manager)
* **[torchbear](https://github.com/foundpatterns/torchbear)** [application framework](https://stackoverflow.com/questions/4241919/what-is-meant-by-application-framework)

Once these are installed, clone the repo with git, run `peru sync` to install its components, and run it with `torchbear`.  To update, use `git pull` and `peru reup`.

### Developing

To modify any functionality in Lighttouch, create a git repo outside of it for the component your are modifying, and add an override in `peru.yaml` so that it will use that source directory.  For example, to modify `lightouch-base`, clone it somewhere else, then run `peru override add lighttouch-base {{ path to lighttouch-base repo }}`.  Then, after making each change to the source, run `peru sync` to update your Lighttouch.
