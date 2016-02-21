# Installing Virtualenv

When we start developing our Django apps, we want to make sure our projects are enclosed in "bubbles" known as virtual environments. 

For example, as of this writing, Django's current version is 1.9. When new versions of Django are released, they may not be backwards compatible with previous versions of Django.

Without a virtual environment, we'd have Django 1.9.2 installed *globally* on our computer, and every Django project you build would use that version. If you wanted to upgrade your version of Django, you'd have to go through every one of your projects to make sure they don't break.

**With a virtual environment, every project can have a separate version of Django and other plugins that you install.** You can install Django 1.9 on one project, and down the line, start another project with Django 1.10. Every project can work off of whatever version of whatever you install, keeping them separate from each other. This is very important when you're programming.

We should already have pip, so we'll use it to install virtualenv *(don't paste
in the* `$` *- it's an indicator that the command below is meant to be run on
your command line utility.)*:

```
$ pip install virtualenv
```
