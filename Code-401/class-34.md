# Class 34: API Deployment

## [Django Settings Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)

---
## Managing Django Settings: Issues
**Different environments**. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

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

In this example you will create a separate file in the 














<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## [SSH Tutorial](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)


## **Additional Resources**

## Review/Skim: [White Noise](http://whitenoise.evans.io/en/stable/)
## Skim: [IaaS](https://en.wikipedia.org/wiki/Infrastructure_as_a_service)
## Skim: [PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service)
## Bookmark: [CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)