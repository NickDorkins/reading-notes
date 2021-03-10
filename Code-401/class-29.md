# Class 29: Django Custom User


## [Django Custum User Model](https://learndjango.com/tutorials/django-custom-user-model)

Setup
To start, create a new Django project from the command line. We need to do several things:

Naviagte to the desired directory:
```
$ cd ~/Desktop
```

create and navigate into a dedicated directory called `accounts` for example:
```
$ mkdir accounts && cd accounts
```
or 
```
$ mkdir accounts
$ cd accounts
```

install Django
```
$ pipenv install django~=3.1.0
```

enter your virtual envirnment:
```
$ pipenv shell
```

make a new Django project called `config`
```
(accounts) $ django-admin.py startproject config .
```

make a new app accounts
```
(accounts) $ python manage.py startapp accounts
```

start the local web server:
```
(accounts) $ python manage.py runserver
```
Here are the commands to run:

> Note that you did not run `migrate` to configure our database. It's important to wait until after we've created our new custom user model before doing so.










































<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## [DjangoX](https://github.com/wsvincent/djangox)

## Additional Resources
## [Creating a Custom User Moel](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)

## [Abstract User, User Profile and Signals in Django](https://www.youtube.com/watch?v=EudKs1HPUfE)

## Bookmark/Skim
## [Substituting a custom User mode](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#auth-custom-user)
