# PyCon tutorial

Hello Web App's material will be tested at [PyCon US
2014](https://us.pycon.org/2014/) in Montreal in a three hour tutorial (yay!)

## Prerequisites 

Make sure you've installed Python and have a very basic understanding of Python
logic (if-statements, loops, variables, comments, etc.)

* [Python installation
  instructions](https://github.com/limedaring/HelloWebApp/tree/master/installation-instructions)
* [Basic Python
  resources](https://github.com/limedaring/HelloWebApp/tree/master/python-tips) 

## Outline

Here's the tentative outline for the course, which is pretty much the exact
outline of the upcoming Hello Web App book. We probably won't cover all topics
but they're here just in case:

* Introductions
* Best practices for planning your web app.
    * MVPs
    * How to narrow down your scope.
    * How launch quickly and why.
* What we're going to build in the tutorial.
    * "Directory of objects"
* Review of pre-requisites and making sure everyone is ready.
    * Very basic knowledge of Python and logic.
        * [Resources to learn](https://github.com/limedaring/HelloWebApp/tree/master/python-tips)
    * Python must already be installed.
        * [Use this guide to install](https://github.com/limedaring/HelloWebApp/tree/master/installation-instructions).
    * Django installed
        * [Guide](https://github.com/limedaring/HelloWebApp/blob/master/installation-instructions/starting-your-project.md)
* Launching the Django application
    * `startproject`
    * `startapp`
    * Add app to INSTALLED_APPS in settings.py
    * Start your Django server
* Playing with templates
    * Set up index.html
        * Create template directory
            * Add index.html, basic boilerplate HTML
        * Add URL definition to urls.py
        * Add view to point to index.html
    * Adding static files
        * Create `static` directory and additional `images`, `css`, and `js`
          sub-folders.
        * Add `/static/` to `STATIC_URL` in settings.py
        * Add `{% load staticfiles %}` to index.html
        * Load static content - `{% static 'css/style.css' %}`
            * Only necessary in templates, use relative paths in CSS files
    * Inheritance
        * Create layout template
            * Create `layouts` folder
            * Duplicate index.html into folder named as base.html
            * Open up base.html and define blocks
                * `{% block title %}{% title %}`
                * `{% block content %}{% endblock %}`
        * Set index.html to inherit from base.html
            * Delete everything that we kept in the base.html file.
            * Add `{% extends 'layouts/base.html' %}`
            * Wrap remaining information in `{% block %}` tags.
            * Check out index.html to confirm it's working
        * Set up additional static pages
            * Duplicate `index.html`
                * `about.html`
                * `contact.html`
            * Set up `TemplateView.as_view` pointing to those files in urls.py
                * e.g.: `url(r'^contact/$', TemplateView.as_view(template_name='contact.html'), name='contact'),`
            * Update content in additional pages.
    * Named URLs
        * Add a nav to our base.html file.
        * Use named URLs to point to about.html and contact.html
            * Why? Because if we change the url of those pages, Django will
              automatically update it for us. Handy dandy.
    * Fun with template tags and template filters
        * Add a variable to your views, pass it to the template.
            * `number = 6`, add to `render_to_response` in index view.
        * Explain how we access variables and do dynamic operations in templates.
            * `{{ variable }}`: Accesses variable.
            * `{% action %}`: Dynamic operation.
                * See loading static content and defining blocks above.
                * Also, for-loops, if-statements, etc.
        * Show variable in the template.
            * `We have {{ number }} objects in our database.`
        * Show an if statement:
            * `{% if number == 6 %}There are indeed 6 objects.{% else %}Not six
              objects.{% endif %}`
        * Open up https://docs.djangoproject.com/en/dev/ref/templates/builtins/
          in browser just for reference (or Google "Django Template Tags")
            * Demonstrate add tag for example:
                * `{{ number|add:"2" }}`
                * pluralize filter: `You have {{ number }} object{{
                  number|pluralize }}`: "You have 6 objects"
                    * Can also have different suffixes:
                        * `You have {{ number }} walrus{{
                  number|pluralize:"es" }}`: "You have 6 walruses"
            * Pass in a sentence in our view
                * `object_name = "Object name"`, add to `render_to_response`
                * slugify filter: `{{ object_name|slugify }}`: "object-name"
                * upper and lower filter: `{{ object_name|lower }}`: "object
                  name" - `{{ object_name|upper }}`: "OBJECT NAME"
                * title filter: `{{ object_name|title }}`: "Object Name"
                * truncatewords: `{{ object_name|truncatewords:1 }}`: "Object
                  ..."
* Adding dynamic data
    * Set up sqlite3 database
        * Only use for development, not good for production.
    * Set up the model
        * What fields do we want to start with?
            * Object name
            * Object description
            * When the object was added/created
        * Add these fields to model
            * `class Object(models.model):`
            * `name = models.CharField(max_length=255)`
            * `description = models.TextField()`
            * `created = models.DateTimeField(auto_now_add=True)`
        * Make sure to change your model name to something unique to
          what you're building, AKA `class Jam(models.model)`
        * More information on model fields, Google for "django model fields"
            * Just like forms, use the right field for the type. BooleanField
              for True/False, DateField, EmailField, URLField, DateTimeField etc.
    * What are migrations and why
        * Think of the database like a big table in Excel (because it basically
          is) - what happens to existing data when we add fields?
        * Make a migration using Django's migrations
            * Command line, `python manage.py makemigrations`
                * Creates a file that we'll apply.
            * `python manage.py migrate`
            * Will create a superuser here for your database as well.
        * Run these two steps every time you add or remove fields from your
          model.
    * Checking out the Django admin
        * http://localhost:8000/admin/, log in using superuser created earlier.
        * Add our model to admin.py
            * `admin.site.register(Object, ObjectAdmin)`
            * `class ObjectAdmin(admin.ModelAdmin): list_display = ('name','description','created',)`
        * Hello visual view of our database!
        * Add example object using the admin.
* Viewing our database items in the template
    * Adding database queries to our view.
        * `objects = Object.objects.all()`, pass to template.
        * Adding a for-loop in our template.
            * `{% for object in objects %}{{ object.name }}{% endfor %}` etc.
    * More queryset fun.
        * Getting the first object.
            * `first = Object.objects.get(id=1)`
            * Add to template
        * Filtering
            * `matches = Object.objects.filter(name__contains='Thing')`
            * Add to template
            * See the rest of Django's queryset filters for more fun!
* Adding more pages to our website
    * Filtered pages for names
        * Add a couple more objects into our admin page
        * Add another URL to urls.py
            * `url(r'^browse/name/(?P<initial>[-\w]+)/$', 'by_name', name='by_name'),`
        * Copy a template file to create search.html
        * Add a basic view
            * `objects = Objects.objects.filter(name__istartswith=initial).order_by('name')`
        * Update search.html to loop over the object names.
    * Specific object pages
        * Add slug field to models
            * `slug = models.SlugField()`
        * Add slug to admin.py
            * `prepopulated_fields = {"slug": ("name",)}`
        * Run makemigrations and migrate (might have issue populating new
          fields)
        * Add to urls.py
            * `url(r'^objects/(?P<slug>[-\w]+)/$', 'object_detail', name='object_detail'),`
        * Add to views.py
            * `def object_detail(request, slug)`
            * `object = get_object_or_404(Object, slug=slug)`
        * Add template page
        * Link to the individual pages from other templates
    * Includes
        * All our object listings are in numerous pages, but we don't want
          repeating code - hard to maintain.
        * Create an includes file
            * Create folder called includes
            * Make search_result.html
            * Copy/paste object search result code in.
        * Add includes code into index and search page
            * `{% include "includes/search_result.html" %}`
    * Contact form
        * Fun with forms.py
    * Error pages
* Editing model information in the website using forms.py

(More coming soon!)

## After the tutorial

Check out [this document for more resources and other tutorials to continue your
programming
education](https://github.com/limedaring/HelloWebApp/blob/master/pycon-tutorial/additional-resources.md)
(big thanks for the folks at [Django Hack &
Learn](https://www.eventbrite.com/e/django-hack-learn-tickets-9900931954) for
helping compile this document.)
