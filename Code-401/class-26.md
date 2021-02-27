# Class 26: Intro to Django

## [Getting started with Django](https://www.djangoproject.com/start/)

- [Django Tutorial](https://docs.djangoproject.com/en/stable/intro/tutorial01/)

- [Django documentation](https://docs.djangoproject.com/)

- [Installation Instructions](https://docs.djangoproject.com/en/stable/intro/install/)
---
## Installing an official release with pip

This is the recommended way to install Django.

Install pip. The easiest is to use the standalone pip installer. If your distribution already has pip installed, you might need to update it if it’s outdated. If it’s outdated, you’ll know because installation won’t work.

Take a look at venv. This tool provides isolated Python environments, which are more practical than installing packages systemwide. It also allows installing packages without administrator privileges. The contributing tutorial walks through how to create a virtual environment.

After you’ve created and activated a virtual environment, enter the command:
```
 $ python -m pip install Django
```
---
## Installing the development version

Tracking Django development

If you decide to use the latest development version of Django, you’ll want to pay close attention to the development timeline, and you’ll want to keep an eye on the release notes for the upcoming release. This will help you stay on top of any new features you might want to use, as well as any changes you’ll need to make to your code when updating your copy of Django. (For stable releases, any necessary changes are documented in the release notes.)

If you’d like to be able to update your Django code occasionally with the latest bug fixes and improvements, follow these instructions:

Make sure that you have Git installed and that you can run its commands from a shell. (Enter git help at a shell prompt to test this.)

Check out Django’s main development branch like so:

```
$ git clone https://github.com/django/django.git
```

This will create a directory django in your current directory.

Make sure that the Python interpreter can load Django’s code. The most convenient way to do this is to use a virtual environment and pip. The contributing tutorial walks through how to create a virtual environment.

After setting up and activating the virtual environment, run the following command:

```
$ python -m pip install -e django/
```

This will make Django’s code importable, and will also make the django-admin utility command available. In other words, you’re all set!

When you want to update your copy of the Django source code, run the command git pull from within the django directory. When you do this, Git will download any changes.

---

Quick example

This example model defines a **Person**, which has a **first_name** and **last_name**:

```
from django.db import models

class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)
```

first_name and last_name are [fields](https://docs.djangoproject.com/en/3.1/topics/db/models/#fields) of the model. Each field is specified as a class attribute, and each attribute maps to a database column.

The above Person model would create a database table like this:

```
CREATE TABLE myapp_person (
    "id" serial NOT NULL PRIMARY KEY,
    "first_name" varchar(30) NOT NULL,
    "last_name" varchar(30) NOT NULL
);
```

Some technical notes:

- The name of the table, myapp_person, is automatically derived from some model metadata but can be overridden. See [Table names](https://docs.djangoproject.com/en/3.1/ref/models/options/#table-names) for more details.
- An id field is added automatically, but this behavior can be overridden. See [Automatic primary key fields](https://docs.djangoproject.com/en/3.1/topics/db/models/#automatic-primary-key-fields).
- The CREATE TABLE SQL in this example is formatted using PostgreSQL syntax, but it’s worth noting Django uses SQL tailored to the database backend specified in your [settings file](https://docs.djangoproject.com/en/3.1/topics/settings/).


## [How Django Works Behind the Scenes](https://wsvincent.com/how-django-works-behind-the-scenes/)

***Django was originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss. The code was open-sourced in 2005 and developers immediately started making contributions to the codebase. Fourteen years later, Django remains under active development, with new [major releases every nine months](https://www.djangoproject.com/download/), minor security releases almost monthly, an [official issue tracker](https://code.djangoproject.com/query), and robust discussion on the [django-developers Google group](https://groups.google.com/forum/#!forum/django-developers).***

## Almost all popular open source packages have some degree of funding involved, typically in one of three forms:

1) **Corporate Sponsor** - A group of engineers within a larger, for-profit company decide to open-source internal code. This is how [React](https://reactjs.org/) (Facebook) and [Angular](https://angularjs.org/) (Google) emerged. Typically engineers at the company are paid, in part, to work on open source though community involvement from developers outside of the core company occurs as well. While this structure has the stability of a wealthy benefactor, there can be [confusion around the licensing aspects](https://engineering.fb.com/open-source/explaining-react-s-license/) at times.

2) **Solo** - An individual developer initially creates code, open sources it, and retains default control. This is the case for [VueJS](https://vuejs.org/), [Tailwind CSS](https://tailwindcss.com/), and [Laravel](https://laravel.com/), among others. Typically the lead developer either raises contributions directly like [Evan You of VueJS](https://github.com/customer-stories/yyx990803), offer add-on services like [Spark for Laravel](https://spark.laravel.com/), or the founders provide highly-paid consulting services.

3) **Non-profit** - This was Django’s approach early on, [in 2008](https://www2.ljworld.com/news/2008/jun/17/new_foundation_django/), when the [Django Software Foundation](https://www.djangoproject.com/foundation/) was formed to promote, support, and advance Django.

## Conclusion

So where does this Django behind the scenes tour leave us? Django’s code is open source and available to all. Django’s organization is managed by a non-profit, the DSF, with a miniscule budget. And Django code is lead by a core team of volunteers, two paid Django Fellows, and a larger group of contributors.

One of the best ways to become more involved in Django is to attend an annual conference and meet all the contributors in person. Currently there are DjangoCons in the [US](https://2019.djangocon.us/), [Europe](https://2019.djangocon.eu/), [Australia](https://2019.pycon-au.org/), and [Africa](https://www.djangoproject.com/weblog/2019/nov/18/introducing-djangocon-africa/) in 2020 for the first time. I hope to see some of you there!

Resources:

[What is Django](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction)

[First Django App - Part 1](https://docs.djangoproject.com/en/3.0/intro/tutorial01/)

[First Django App - Part 2](https://docs.djangoproject.com/en/3.0/intro/tutorial02/)