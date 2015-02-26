# Installing Python 2.7 on Windows

First off, a disclaimer - development on Windows will be harder than if you were
on Linux or Mac. If you can, I'd recommend installing Linux on your systerm and
using that instead. 

## Using the command line

First, are you comfortable with the command line? It's infinitely simpler to
download and install utilities using the command line, so if you
haven't used the command line before, try out [The Command Line Crash
Course](http://cli.learncodethehardway.org/book/) by the same author who wrote
[Learn Python the Hard Way](learnpythonthehardway.org). Should only take a day
or so to go through all the lessons.

## Installing Python

This tutorial will be more fully fleshed out soon - in the meanwhile, [use this
tutorial for installing Python on
Windows](http://docs.python-guide.org/en/latest/starting/install/win/). This
tutorial will also install *pip* on your computer, which is also needed by Hello
Web App.

Make sure to follow the instructions at the [end of the tutorial to install
virtualenv.](https://github.com/kennethreitz/python-guide/blob/master/docs/dev/virtualenvs.rst)

*(Thanks to Kenneth Reitz for these instructions.)*

## Installing msysgit

Hello Web App uses unix commands like *touch* to create files from the command
line, which doesn't exist on Windows. We need git anyways for our project, so
install [msysgit](https://msysgit.github.io/) which'll install git on your
computer as well as allow you to use unix commands like *touch*.

(If you need more here, [this is another tutorial with pretty detailed
instructions on installing
msysgit](http://lostechies.com/jasonmeridth/2009/06/01/git-for-windows-developers-git-series-part-1/).)

- - -

You're finished setting up your system!

But wait, you may be thinking - what about installing Django? We're going to
install Django on a project-by-project basis (within the virtual environment
provided by virtualenv). [Follow those instructions
here.](https://github.com/limedaring/HelloWebApp/blob/master/installation-instructions/starting-your-project.md)
