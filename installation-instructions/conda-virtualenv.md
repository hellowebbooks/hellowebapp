### Start your virtual environment in conda

If you're using Conda you'll get an error when you try to `pip install virtualenv`.
That's because Conda is a virtual environment manager as well as a package manager.
Now that you're within your empty project folder, create your virtual
environment:

    conda create --name venv python

And then activate the environment:

    source activate venv

You should see something like this in your command line before the folder
structure - the (venv) indicates you're in the virtual environment:

    (venv)limedaring@Orion ~/projects/hellowebapp $

/(Orion is my computer's name and limedaring is my username - your exact setup
will be different.)

Now you're in your bubble, so we can start installing project-specific utilities.
If you ever need to deactivate your environment, run

    source deactivate

And now on to [installing Django](https://github.com/hellowebapp/hellowebapp/tree/master/installation-instructions/starting-your-project.md#install-django).
