---
title: Best Practices
---

# Best Practices

## Version Control

If you are new to programming, or writing scripts to run a scientific analysis,
it's essential to start using version control. 

{% include alert.html title="What is version control?" type="question" content="Version control is like having
a well organized, Mary Poppins-esche recipe box that can summon up any previous version of your code on demand, and multiple people can interact with contents without bumping heads. More formally, it means tracking changes in your source code over time. You can work on multiple features at once, and multiple people can collaborate on the same code base without issue." %}

If you want to do reproducible research, this is the first step, as
reproducible science calls for keeping a history of your work. Any kind of text file that
can be stored in a repository is fair game.

{% include alert.html title="What is a repository?" type="question" content="A repository, or sometimes referred to as a repo, comes down to a folder of files and subfolders that has a hidden folder, (usually .git) that stores history, branches, and other metadata about the project." %}

In practice, this means that you keep an entire history of your work. It means that collaboration is easy - you
can make changes without worrying about overriding someone else's. If an error is introduced
into the codebase, you can revert to a previous version. It makes it easy to associate
versions with release tags, so someone installing your software can reliably use the 
right version. It's also a lot of fun! Platforms like [GitHub](https://www.github.com) and [GitLab](https://www.gitlab.com)
have nice interfaces and facilitate fun interactions. Maintaining code is an interactive,
and fulfilling experience. It will help you whether you are working on your own,
or on a large project with many others.


### Services

When you create a repository on your local machine, you can create a remote version of it
that you push and pull changes from along with others working on the project. Thus,
the first thing you would want to do is sign up for one of these remote services.

 - **Recommended** [GitHub](https://www.github.com) has become a leader in version control, with great support for open source and the academic community.
 - **Others** include [GitLab](https://www.gitlab.com) and [BitBucket](https://bitbucket.org). Often, you might want to check with your group about what version control service they use. Since the underlying technology, [git](https://git-scm.com/), is shared between these services, while signing up for an account to participate on the platform would be required, there isn't any reason you can't jump around between them, even with the same code bases. This is possible, although not recommended.

### Getting Started with Version Control

We don't need to post getting started instructions here because there are many already
available!

 - [Software Carpentry](http://swcarpentry.github.io/git-novice/) offers a git novice course, and it's also available [in Spanish](https://swcarpentry.github.io/git-novice-es/).
 - [try.github.io](https://try.github.io/) has a listing of resources to learn by doing, reading, or participating.
 - [Best Practices](https://github.com/trein/dev-best-practices/wiki/Git-Commit-Best-Practices) exist for writing commit messages, which are little messages that you add when you want to save the current state of your repository.
 - [Understanding the GitHub Flow](https://guides.github.com/introduction/flow/) gives a nice overview of all the terms and how to manage a repository.

{% include alert.html title="How do I get started?" type="tip" content="By far, the best way to get started is to read about the basics, and then create an account and jump in! if you can't find the answer to a question, just ask." %}

## Testing and Code Coverage

It's easy to write a function, and then make a change somewhere else, and your function
breaks (and perhaps you don't notice). To prevent this from happening, we can
regularly test our software. If we want to add new code? We test that everything still works.
When it's time for a release? We ensure that everything builds.
There are three main types of testing, and of the three, two are essential:

### Unit Testing

Unit testing means breaking your code down into small components (e.g., a function to read a file)
and then testing that component. When you add a new function or feature, it should be standard to 
write tests for it.

### Regression Testing

Regression testing is about consistency. We want to ensure that if you give your software the
same input over time, it returns the same value.


### Recommended Libraries

 - **Python**: while there is the module unittest and several deprecated, we recommend using [pytest](https://pytest.org/en/latest/) for easy writing and running of tests. [Here](https://www.tutorialspoint.com/pytest/pytest_introduction) is a tutorial to get started.
 - **R**: you can use [testhat](https://testthat.r-lib.org/).
 - **C/C++/Fortran**: you can use [CTest](https://gitlab.kitware.com/cmake/community/wikis/doc/ctest/Testing-With-CTest).
 - **Matlab**: provides a [list of resources](https://www.mathworks.com/help/matlab/matlab-unit-test-framework.html) for testing.

## Continuous Integration (CI)

Continuous integration comes down to automation. It means that there is a service that might build,
test, and deploy your code. When does it happen? It depends how you set it up. It might
happen when someone puts in a request to change the code (called a Pull Request) and you
want to ensure everything builds and tests ok before merging to master. It might run when
a change is commit to the master branch. The general idea is to catch bugs before they
reach anyone. How do they work? Most of the time, they can integrate with webhooks
(notificaations) that are sent from your version control services.

### CI Services

It's recommended to find CI services that offer "free for open source" and
integration with common web-based version control sources like GitHub. The recommended
services are:

 - [Circle CI (Linux)](https://circleci.com)
 - [Travis CI (Linux/Mac OSX)](https://travis-ci.org/)
 - [Appveyor (Windows)](https://www.appveyor.com/)


{% include alert.html title="How do I get started?" type="question" content="It's recommended to look at other projects with similar code that are set up with the service that you chose, and modify to your need. If you need some help and want the setup done for you, we can help." %}


## Code Style

Do you use spaces or tabs? Is there a newline after function declarations, or
docstrings? How are modules organized? These details encompass what we refer to as code style. 
Style is important not only for aesthetic, but so other developers
can quickly find what they are looking for. It makes it easy for you to find
a new code base, and quickly start working on it. 

### Style Guides
While much of your style can be personal, a few languages have well established style guides:

 - [Python Style Guide](https://www.python.org/dev/peps/pep-0008/)
 - [GoLang](https://github.com/golang/go/wiki/CodeReviewComments)
 - [Google Style Guide](https://google.github.io/styleguide) includes C++, objective C, Python, Java, R, Shell, HTML/css, and more.

### Formatters

Some languages come with formatters that can help to automatically format your code.
Always keep a back up if you are worried about the output or using the tool for
the first time.

 - [Python YAPF (enforces PEP8)](https://github.com/google/yapf)
 - **C/C++**: [clang-format](https://clang.llvm.org/docs/ClangFormat.html) and [astyle](http://astyle.sourceforge.net/)
 - **R**: [styler](https://www.tidyverse.org/articles/2017/12/styler-1.0.0/) or [formatR](https://yihui.name/formatr/)

### Linters

If you are uncomfortable with a script changing your code, you can also use a linter.
Linters will check over your code statically, and print any issues that are seen,
and can be customized with configuration files. For example, if you have well
formatted code and want to check that contributions follow suite, even if you
use an automated tool to format, you would want to have the code linted during 
testing to make sure that the contributions were also formatted correctly.

 - [golint for GoLang](https://github.com/golang/lint)
 - [Python flake8](http://flake8.pycqa.org/en/latest/)
 - [Python pep8](https://pep8.readthedocs.io/en/release-1.7.x/)


## Documentation

What are you reading _right now_? It's documentation, of course, and it's essential
to make your software easy to use. When you've written a code base and are well familiar
with function execution, parameters, and application flow, it can be easy to forget
that anyone else using your software hasn't a clue. If you have an entrypoint with 
a `--help` command it might be a good starting point, but beyond that, you need to write
documentation. There are two questions to ask here - what kind of content should
I include, and how can I easily share it?

### Content

It's helpful to put yourself in the shoes of a new user. Perhaps you've just discovered
the GitHub repository with the code, what do you do first? Are there dependencies needed
on the system? How does the user clone the repository and install your software?
While every software project is a little different, you very likely will need to discuss
the following:

 - How do I get everything I need on my machine (e.g., git clone...)
 - What are dependencies for the software?
 - How do I compile/build/test/install?
 - How do I get started?


{% include alert.html title="Make it easy to get started" type="tip" content="For the last point, it's good to provide the user with a Getting Started link directly after they have installed the software. It should serve as a toy example of using your software, and give them a base to grow." %}

### Code Documentation

While some might argue that "code should comment itself" for the most part, this
isn't true. It's unfortunately easy to write code, come back a few months later,
and not completely remember what you were thinking at the time. Thanksfully,
this can be helped with commenting. Along with writing [docstrings](https://en.wikipedia.org/wiki/Docstring),
or definitions for functions that include descriptions, inputs, and outputs, it's helpful
to comment your code. While naming variables so the function is intuitive is helpful,
commenting can help to add notes for future developers about design decisions, or 
items remaining TODO. It might even be appropriate to link to a GitHub issue for 
a dependency that, at the time of writing, isn't resolved. At some future
time point someone else can check the issue for resolution, and update the
dependency accordingly.

### Documentation Tools

The choice of a documentation tool depends upon your intended use case. 

#### Static Generators
If you just want to write a user guide or tutorial (and don't want to render documentation
from the docstrings in your code) you can use a static site generator, such as [Jekyll](https://jekyllrb.com)
on [GitHub pages](https://pages.github.com/). This is an optimal strategy because it means that versioned 
documentation will live alongside code. There are also a large number of [beautiful themes](https://jekyll-themes.com/)
that you can get started with.

#### Static Generators for Code

If you want to render documentation from the docstrings in your code, you could do this
alongside a static site renderer, or start with the rendered code documentation as a base
to add tutorials and other custom content to. Here are a few popular generators of this type:

 - [Python Sphinx](http://www.sphinx-doc.org/en/stable/) can be deployed on [readthedocs](https://www.python.org/dev/peps/pep-0008/)
 - [Roxyen2 for R](https://cran.r-project.org/web/packages/roxygen2/vignettes/roxygen2.html)


Would you like to see another guide? Please [let us know]({{ site.repo }}/issues/new).
