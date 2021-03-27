# Class 34: API Deployment

## [Django Settings Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)

---
## Managing Django Settings: Issues
**Different environments**. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: `DEBUG = True`, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

**Sensitive data**. You have `SECRET_KEY` in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.

**Sharing settings between team members**. You need a general approach to eliminate human error when working with the settings. For example, a developer may add a third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.

**Django settings are a Python code**. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

---

## Setting Configuration: Different Approaches

**There is no built-in universal way to configure Django settings without hardcoding them.**

### **settings_local.py** - Old school but still effective

The idea behind this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.

<br><br>

**Example:**

### **settings.py** (Project)

```
ALLOWED_HOSTS = ['example.com']
DEBUG = False
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'production_db',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db.example.com',
        'PORT': '5432',
        'OPTIONS': {
            'sslmode': 'require'
        }
    }
}

...

from .settings_local import *
```

> Notice the import on the last line, this is importing an override of the settings that are hard coded in the regular settings file

<br><br>

### **settings_local.py** (Local Scope Settings)

```
ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```

| Pros: | Cons: |
| --- | --- |
| Secrets not in VCS. | settings_local.py is not in VCS, so you can lose some of your Django environment settings. |
| --- | The Django settings file is a Python code, so settings_local.py can have some non-obvious logic. | 
| --- | You need to have settings_local.example (in VCS) to share the default configurations for developers. | 


---
---

### **Separate settings file for each environment**

This method extends on the previous method as it allows you to keep all configurations in the Version Control System (VCS) and to share default settings between developers.

### In this example you will create a separate file in the settings **folder**:

<br><br>

settings/

```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py
```

<br><br>

settings/local.py

```
from .base import *


ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```

<br><br>

To run a project with a specific configuration, you need to set an additional parameter:

```
python manage.py runserver --settings=settings.local
```

| Pros: | Cons: |
| --- | --- |
| All environments are in VCS. | You need to find a way to handle secret passwords and tokens. |
| It’s easy to share settings between developers. | “Inheritance” of settings can be hard to trace and maintain. |

---

### **Environment variables**

To solve the issue with sensitive data, you can use environment variables.
import os

```
SECRET_KEY = os.environ['SECRET_KEY']
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ['DATABASE_NAME'],
        'HOST': os.environ['DATABASE_HOST'],
        'PORT': int(os.environ['DATABASE_PORT']),
    }
}
```

> This is the simplest example using Python os.environ and it has several issues:
>
> - You need to handle KeyError exceptions.
> - You need to convert types manually (see DATABASE_PORT usage).

To fix KeyError, you can write your own custom wrapper. For example:

```
import os

from django.core.exceptions import ImproperlyConfigured


def get_env_value(env_variable):
    try:
      	return os.environ[env_variable]
    except KeyError:
        error_msg = 'Set the {} environment variable'.format(var_name)
        raise ImproperlyConfigured(error_msg)


SECRET_KEY = get_env_value('SECRET_KEY')
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': get_env_value('DATABASE_NAME'),
        'HOST': get_env_value('DATABASE_HOST'),
        'PORT': int(get_env_value('DATABASE_PORT')),
    }
}
```
> Also, you can set default values for this wrapper and add type conversion. But actually there is no need to write this wrapper, because you can use a third-party library.

| Pros: | Cons: |
| --- | --- |
| Configuration is separated from code. | You need to handle sharing default config between developers. |
| Environment parity – you have the same code for all environments. |
| No inheritance in settings, and cleaner and more consistent code. |
| There is a theoretical grounding for using environment variables – 12 Factors. |

---
---

## 12 Factors

12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.

As the name suggests, the collection consists of twelve parts:

- Codebase
- Dependencies
- Config
- Backing services
- Build, release, run
- Processes
- Port binding
- Concurrency
- Disposability
- Dev/prod parity
- Logs
- Admin processes











<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## [SSH Tutorial](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)


## **Additional Resources**

## Review/Skim: [White Noise](http://whitenoise.evans.io/en/stable/)
## Skim: [IaaS](https://en.wikipedia.org/wiki/Infrastructure_as_a_service)
## Skim: [PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service)
## Bookmark: [CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)