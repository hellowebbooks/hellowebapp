# Installing Python on Linux

## Using the command line

First, are you comfortable with the command line? It's infinitely simpler to
download and install utilities for your Mac using the command line, so if you
haven't used the command line before, try out [The Command Line Crash
Course](http://cli.learncodethehardway.org/book/) by the same author who wrote
[Learn Python the Hard Way](learnpythonthehardway.org). Should only take a day
or so to go through all the lessons.

## About Linux Distributions

There are quite a number of different flavors of Linux. The two most common types are Debian-Based, and Fedora. Be sure to find out what type of distribution you have before proceeding. If you have Ubuntu or Mint, follow the instructions for Debian-based distributions. If you have Fedora, follow the instructions for Fedora.

## Making sure everything is up to date

First, we should make sure that everything in our system is up to date before we install any packages.

On Debian-based distributions:

```
sudo apt-get update
```

On Fedora:
```
yum check-update
```

On Debian-based distributions, you'll have to use sudo (super user do) when you install the packages listed on this page. Be careful when using sudo, as you're calling super-user rights which can land you in hot water if you're not sure what you're doing. 

## Installing Setuptools

Debian-based and Fedora distributions come with Python pre-installed, which means you don't need to install Python at all. However, [Setuptools](https://pypi.python.org/pypi/setuptools#unix-wget) is a fairly important Python package, which you should install before you do anything else. 

On Debian-based distributions: 

```
sudo apt-get install python-setuptools
```

On Fedora:
```
yum install python-setuptools
```

## Installing git

The next thing we need to have installed is [git](http://git-scm.com/), which is
a version control system. You can work on your programming projects while
committing versions, allowing you to roll back easily if something you do
breaks. git also works with GitHub, so you can save your project to the
"cloud", backing it up as well as allowing others to work on the same project
with you.

On Debian-based distributions:

```
sudo apt-get install git
```

On Fedora:
```
yum install git
```

We'll go over some of these basics in the book, but if you'd like to do some
advanced reading on git basics, [check out this
guide](http://git-scm.com/book/en/Git-Basics).

## Installing pip

[pip](http://www.pip-installer.org/en/latest/) is essentially a package manager for Python packages. 

On Debian-based distributions:
```
sudo apt-get install python-pip
```

## Installing virtualenv

Another thing we need installed is
[virtualenv](http://www.virtualenv.org/en/latest/virtualenv.html). virtualenv
allows you to set up virtual environments for all of your programming projects -
essentially, a bubble which wraps around projects and their package installs,
preventing them from interfering with each other. 

For example, if you install Django 1.6 globally on your computer, every project
will be using Django 1.6 - and when you upgrade to 1.7, you'll upgrade every
project as well, potentially breaking them due to deprecated features.
virtualenv keeps projects separate - you can have one project on Django 1.6 and
another on 1.7, and they won't interfere with eachother.

We already have pip, so we'll use it to install virtualenv:

```
sudo pip install virtualenv
```

We'll go over this again when we officially start our Hello Web App project, but
to use virtualenv, you'll move into the directory where your project lies and
run `virtualenv --distribute venv`, which'll create the virtual environment.  To
activate the environment, you'll run `source venv/bin/activate`, and
`deactivate` to deactivate. While in the environment, we can use pip to install
and uninstall everything we need without worrying about it conflicting with any
other project.

- - -

You're finished setting up your system! 

But wait, you may be thinking - what about installing Django? We're going to
install Django on a project-by-project basis (within the virtual environment
provided by virtualenv). [Follow those instructions
here.](https://github.com/limedaring/HelloWebApp/blob/master/installation-instructions/starting-your-project.md)
