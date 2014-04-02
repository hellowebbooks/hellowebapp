# After the tutorial resources

Congrats on making it through the tutorial! This document contains some fun
things that you might want to poke at after the tutorial - additional Django
tutorials, information on databases, and more.

If you'd like to add anything to this list, just send a pull-request or email me
at tracy@limedaring.com!

## Front-end Design Resources:

* **CSS Frameworks** — helps you with a framework for your website, with widgets
  like drop-downs and grids already built.
    * [http://getbootstrap.com/](http://getbootstrap.com/) - more designed and
      easy to get started with, should probably edit the design a bit on your
own from the default.
    * [http://foundation.zurb.com/](http://foundation.zurb.com/) - more powerful
      and easier to extend but not as easy to get started with.
* **CSS Processors**: Allows you to make functions with CSS and more
    * LESS CSS: [http://lesscss.org/](http://lesscss.org/)
    * Compass (which uses Sass)
      [http://compass-style.org/](http://compass-style.org/) 
    * Sass: [http://sass-lang.com/](http://sass-lang.com/)
        * Both are great. Bootstrap above uses LESS, some people say that Sass
          is easier to use.
* **HTML5 Bootstrap:** Userful to generate HTML templates so you don’t have to
  write them entirely from scratch[.
](http://www.initializr.com/)[http://www.initializr.com](http://www.initializr.com/)
* **Design resources:**
    * Book: Design for Hackers:
      http://www.amazon.com/Design-Hackers-Reverse-Engineering-Beauty/dp/1119998956
    * [https://hackdesign.org/](https://hackdesign.org/) — online design courses
* **Design inspiration:**
    * [http://www.cssmania.com/](http://www.cssmania.com/)
    * [http://www.siteinspire.com/](http://www.siteinspire.com/)
    * [http://www.thebestdesigns.com/](http://www.thebestdesigns.com/)
    * [http://unmatchedstyle.com/](http://unmatchedstyle.com/)
* **Front end testing:**
    * [http://silverbackapp.com/](http://silverbackapp.com/)
* Keep in mind that your app’s design can be really, really basic — just keep it
  clean and make sure it works well, and you can always improve the interface
later!

## Front-end Javascript Packages:

* **Javascript Frameworks:** jQuery (recommended), Google Closure (very
  advanced, should only be considered for huge applications)
* **MVC frameworks:** Angular.js, Ember.js, backbone + underscore.js
* **Frontend templating:** Mustache.js, Handlebars.js

## Picking your DB:

* **SQL:** PostgreSQL (most reliable), MySQL (available on most shared hosting),
  SQLite (convenient for development but do not use for production, will fail
with more than 1 user)
* **NoSQL:** MongoDB, Riak, CouchDB, Redis, Cassandra (Probably a good idea to
  avoid these unless you know what you’re doing)

## Cool Django Plugins:

* **South:** useful for dealing with django migrations (built into Django since
  1.7) - data migration, so you can add new info to your models and have your
databases smoothly add extra columns without breaking extra data.
* **Celery:** Useful for creating tasks that can be scheduled or creating
  methods that can be launched asynchronously (not blocking)
* **Haystack:** Text search for Django (need to supply your own search backend)
* **Django-Registration:**
  [https://pypi.python.org/pypi/django-registration](https://pypi.python.org/pypi/django-registration)
* Working with images? Use **Pillow**:
  [https://pypi.python.org/pypi/Pillow/2.3.0](https://pypi.python.org/pypi/Pillow/2.3.0)
* **Tastypie:** API creation. https://django-tastypie.readthedocs.org/en/latest/	
* Find more at
  [https://www.djangopackages.com/](https://www.djangopackages.com/) !

## Django resources:

* Django best practices book, **Two Scoops of Django**: [http://www.amazon.com/Two-Scoops-Django-Best-Practices/dp/1481879707](http://www.amazon.com/Two-Scoops-Django-Best-Practices/dp/1481879707)
* **[DjangoPackages.com](http://DjangoPackages.com)**

## Ask questions and make friends on IRC:

* Use IRC and want to ask someone a python/django question? 
    * **#positivepython** on freenode is great.
    * **#pyladies**
* Want to use IRC? [http://freenode.net/using_the_network.shtml](http://freenode.net/using_the_network.shtml)
* Clients:
    * Mac: [http://limechat.net/mac/](http://limechat.net/mac/)
    * Mac: [http://colloquy.info/](http://colloquy.info/)
    * PC/Linux: [http://xchat.org/](http://xchat.org/)
    * PC: [http://www.mirc.com/](http://www.mirc.com/)

## Want more Django tutorials?

* [http://gettingstartedwithdjango.com/](http://gettingstartedwithdjango.com/) — video/screencast tutorial
    * Older videos by same author: [http://gettingstartedwithdjango.com/pages/gigantuan/](http://gettingstartedwithdjango.com/pages/gigantuan/)
* [http://www.tangowithdjango.com/](http://www.tangowithdjango.com/)
* [http://effectivedjango.com/tutorial/](http://effectivedjango.com/tutorial/)
* [http://hellowebapp.com](http://hellowebapp.com) (launching in June, Tracy’s shameless plug)

## Launching your project:

* **Heroku**, hosting platform
    * [http://devcenter.heroku.com/articles/django](http://devcenter.heroku.com/articles/django)
    * [https://mike.tig.as/blog/2012/02/13/deploying-django-on-heroku/](https://mike.tig.as/blog/2012/02/13/deploying-django-on-heroku/)
* **AWS,** Amazon Webservices
* Google AppEngine

## Tools:

* **Version Control:** Git (e.g. github, bitbucket)
* **Text Editors:** [Sublime Text 2](http://www.sublimetext.com/2) (Mac), [TextMate 2](http://macromates.com/) (Mac, rumoured to be deadware [maintained by the open source community](https://github.com/textmate/textmate)), Vim, Emacs, Notepad++
    * MacVim (Vim for Mac) is great and free: [https://code.google.com/p/macvim/](https://code.google.com/p/macvim/)
    * Vim and Emacs are hard to learn (can take weeks to get proficient) but very powerful. Probably better to start with something else unless you love learning complex new tools.
        * **Vim tutorials:** (MacVim allows you to do regular commands like ctrl-v and using your mouse along with vim commands, which makes vim easier to use for beginners)
            * [http://www.danielmiessler.com/study/vim/](http://www.danielmiessler.com/study/vim/)
            * http://www.openvim.com/tutorial.html
* **Python IDEs:** Pycharm, xcode, eclipse, anaconda 
* **Handing development environments:** virtualenvwrapper
    * Note: there’s a lot of configuration if you’re using a non standard filepath and not particularly recommended with Anaconda
* **Handling python requirements:** pip, easy_install
* **Database inspection:** SequelPro, Mongohub
* **Python Shells:** ipython, bpython
* **Editing on a remote server:** Macfusion, ssh
* **PEP8:** Not quite a tool, but make sure your Python code is pretty and usable by using the Python Style Guide: http://legacy.python.org/dev/peps/pep-0008/

## Starting a new project? Some general advice:

* **Launch Quickly!**
    * **Figure out your MVP** (minimum viable product) — the very smallest set of features you’d need to have a workable app, and launch.
        * Likely, your future features will change/update once you work with real customers. 
    * Don’t fall in the trap of not launching out of fear, feeling like you don’t have enough features, etc etc. :)
    * Learn to strike a balance between doing things the right way vs. doing things quickly because they need to get done.
    * Unit tests are great! But if your code is changing too quickly, tests may not be useful.
* **Be careful about database calls** — can severely slow down your web app if you do too many. Database calls are any time you’re pulling info from the database — doing a filter() or model.objects.all(), etc.
    * Check out select_related and prefetch_related when you’re making your QuerySets: [https://docs.djangoproject.com/en/dev/ref/models/querysets/#select-related](https://docs.djangoproject.com/en/dev/ref/models/querysets/#select-related)
    * Still too slow? Consider [caching](https://docs.djangoproject.com/en/dev/topics/cache/)
* **Break it down into the tiniest pieces possible and tackle each piece one-by-one.**
    * Figure out the easiest way to tackle each piece (and if any pieces you can do without any coding at all. Keep it simple.)
    * For example, building a site where you list your favorite jams: 
        * You’ll need a model to hold the jam information (name of jam, description of jam, perhaps an image).
        * You’ll need a page that shows all the jams added to the database, with a view powering that page. Make sure to add this URL to urls.py.
        * You’ll need a page for each individual jam, with a url.py entry pointing to it and a view powering it.
        * You can add new jams using the admin, but maybe you’ll want to make a page on your website with a form to add new jams.
            * Which might need a confirmation/success page.
        * Etc. etc. etc. Break it down into pieces, tackle individual pieces, ask for help and google madly if needed. :)
