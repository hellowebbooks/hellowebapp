# Installing Python on Mac

## Using the command line

First, are you comfortable with the command line? It's infinitely simpler to
download and install utilities for your Mac using the command line, so if you
haven't used the command line before, try out [The Command Line Crash
Course](http://cli.learncodethehardway.org/book/) by the same author who wrote
[Learn Python the Hard Way](learnpythonthehardway.org). Should only take a day
or so to go through all the lessons.

## Installing XCode

Unfortunately the native Python that comes on Macs isn't great for development,
so we'll need to install GCC, which'll set your computer up to be able to
download Python.

*Do you have XCode installed already? If so, skip this section. Don't know what
I mean? You likely don't have it installed.*

* Mac OS X 10.9 / Mavericks: [Follow this super simple guide to install Command
  Line Tools from the command line](http://www.computersnyou.com/2025/2013/06/install-command-line-tools-in-osx-10-9-mavericks-how-to/).
* Mac OS X 10.6-10.8 / Mountain Lion, Lion, and Snow Leopard: 
[Follow this guide to install OSX GCC.](https://github.com/kennethreitz/osx-gcc-installer#readme)

## Installing Homebrew

[Homebrew](http://brew.sh/) is a *package manager*, which'll allow you to download and install
packages like Python directly from the command line. 

Open up your terminal and paste this in:

```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

The script should walk you through the rest of installing Homebrew. The last
thing we need to do is insert the Homebrew directory at the top your `PATH`
environment variable. The `$PATH` environment variable is essentially a list of
locations your terminal looks for commands in, and we want Homebrew to be at the
top. 

Run this command in your terminal, which'll do the above for you:

```
echo 'export PATH=/usr/local/bin:/usr/local/sbin:$PATH' >> ~/.bashrc
```

## Installing Python

Now that we have Homebrew, we'll use it to download Python 2.7, which is the
default Python version installed by Homebrew.

```
brew install python
```

## Installing git

The last thing we need to have installed is [git](http://git-scm.com/), which is
a version control system. You can work on your programming projects while
committing versions, allowing you to roll back easily if something you do
breaks. git also works with GitHub, so you can save your project to the
"cloud", backing it up as well as allowing others to work on the same project
with you.

Since we have Homebrew installed, it's easy to install git:

```
brew install git
```

We'll go over some of these basics in the book, but if you'd like to do some
advanced reading on git basics, [check out this
guide](http://git-scm.com/book/en/Git-Basics).

## Installing pip

[pip](http://www.pip-installer.org/en/latest/) is essentially Homebrew for
Python packages, which was already installed when Homebrew installed Python.
Yay!

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
pip install virtualenv
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
