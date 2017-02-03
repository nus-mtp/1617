---
layout: page
title: On Software Implementation
---

# Lecture 4: On Software Implementation
3 February 2017

In this lecture, I am going to run through what you are expected to do during the implementation phase of the project.  Here are the steps:

1. Pick a task / user story
2. Write code to complete the user story
3. Lint and beautify your code
4. Write test cases
5. Repeat 2-4 until it passes the test cases
6. Commit your code
7. Issue a pull request
8. Code review by a teammate
9. (Automated) CI test and deploy

## 2. Writing Code

The implementation phase of your project is not just about writing code that runs correctly.  It is also about **communicating with other developers** using source code, comments, commit messages, API documentation etc.  Getting the code to compile and run correctly is just a small part of the process.  Take time to communicate properly.

Your reputation as a software engineer depends on the quality of your code.   Think of your github account as your resume.

This is a good time to review your CS2103's Handouts/Slides on _Good Code, Bad Code_.

Some properties of good code includes:

* Correct
* Changeable
* Readable (by human)
* Extensible
* Maintainable ([Boehm's curve](http://www.agile-process.org/change.html); common to have a cost of 100:1 after delivery)

[Check out Page 1-2 of the _Clean Code Cheat Sheet_](http://www.planetgeek.ch/2013/06/05/clean-code-cheat-sheet/) for the
dos and don'ts for writing clean code.

Advices:
* Don't try to be clever or terse
* Make your code self-explanatory (write as little comment as possible)
* Comments are for high-level descriptions (what and why)
* Use English
* Don't be afraid of long names (thanks to autocomplete)

You can learn to write good, clean, code by:
* practice: write and rewrite
* read good code from others

### 3. Linting and Formatting

A linting tool performs static analysis on your code to check for style inconsistency, ensure good and professional coding habits, and identify potential bugs.  Think of it as a _computer-assisted code review_.

Your favorite language should have a linting tool.  For instance,

* [```eslint```](http://eslint.org) for Javascript
* Android Studio comes with its own ```lint```
* [```phpcs```](http://pear.php.net/package/PHP_CodeSniffer/redirected) and [others](http://phpqatools.org)

Most of these tools allow configuration of rules -- what do you want to, or do not want to, detect.

Your team should also adopt a consistent coding style.  You can find existing tools that indent/format your code.  To ensure consistent coding style, use a beaufitier, which can automatically
reindent and reformat your code following a given configuration (e.g., use
spaces or tab, how much to indent, etc.)

The following might be useful:

* [```js-beautify```](https://www.npmjs.com/package/js-beautify)
* [```jalopy```](https://github.com/lukespragg/jalopy) is for Java
* [```php-cs-fixer```](https://github.com/friendsofphp/PHP-CS-Fixer) fixes coding style for PHP, while [```php-formatter```](https://github.com/mmoreram/php-formatter) formats the code.

Android Studio comes with built-in indenter, but I find them less configurable than CLI tools in general.

Don't underestimate the importance of indentation ([see Apple's goto fail bug](http://www.wired.com/2014/02/gotofail/))

### 4. Writing Test Cases
* The goal of writing test cases is to have a peace of mind that your changes did not break anything.
* You need to automate the testing process as much as possible, and write the test cases while your code.
* There are many tools and libraries for testing.  The framework you choose should have at least one.

### 6. Commit Your Code

You should:
* commit often
* commit related changes together and unrelated changes separately (```git app -p``` or use a GUI)
* [write good commit message](https://github.com/erlang/otp/wiki/Writing-good-commit-messages).  See [good practices](http://www.slideshare.net/TarinGamberini/commit-messages-goodpractices) by Tarin Gamberini here. In your commit message, describe specifically what has changed and **why**
* NOT commit generated files (```*.class```) nor external libraries (e.g., ```node_modules```) into your repository.

Your team should establish a git repo convention.  Normally, you would want to have a ```master``` branch that contains only approved (has been code-reviewed) and stable code.  Development should occur on feature branches, which is merged into the ```master``` after issuing a pull request and had that request reviewed.
Atlassian has a nice article on such [feature branch workflow](https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow).

### 7. Pull request
* After committing your code into a feature branch, [issue a pull request on Github](https://help.github.com/articles/creating-a-pull-request/)
* Someone else on your team should be responsible for reading through the code, comment on it, and approve it for merging into the ```master``` branch.

### 8. Code review

Why is code review important?
* "Rigorous inspections can remove up to 90% of errors from a software product before the first test case is run." -- “Facts and Fallacies of Software Engineering,” Robert Glass.
* "The average defect detection rate is only 25% for unit testing, 35% for function testing, and 45% for integration testing. In contrast, the average effectiveness of design and code inspections are 55 and 60%." -- - “Code Complete,” Steve McConnell.

Best practices of code review [by SmartBear](http://smartbear.com/SmartBear/media/pdfs/WP-CC-11-Best-Practices-of-Peer-Code-Review.pdf)

  * review small chunk (<400 lines) at a time
  * take you time
  * author should make sure code is ready before review (self-review, tested, make code readable)
  * keep a checklist of common errors
  * be positive (finding bugs is a good thing)


### 9. Continuous integration

Integrate your code with the rest and test as soon as you push.  This allows:

* Everyone can see everything
* You know what is broken immediately and can fix immediately
* Contrast to: integrate at the end (usually crunch time) and you do not know whether it will work!  (e.g., HealthCare.gov launch disaster).
* Keep the build/test process fast
* Commit often, push often (to the main branch)

* Read [Martin Fowler's excellent article on CI](http://www.martinfowler.com/articles/continuousIntegration.html)

### Bonus: Virtual Development Environments

[Vagrant](https://www.vagrantup.com) is a really cool and simple way of creating a virtual development environment.  It allows a developer to easily setup and teardown an environment when switching between different projects, ensures different developers on the same team work on the same environment (even if they run different OSes), and simulate deployment environment locally.  

You can choose from a large catalogue of
[boxes](https://atlas.hashicorp.com/boxes/search), which are basically pre-configured virtual development environments.
