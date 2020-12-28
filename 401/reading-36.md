# Configuring Django Settings: Best Practices
https://djangostars.com/blog/configuring-django-settings-best-practices/Keep settings in environment variables.

Keep settings in environment variables.

Write default values for production configuration (excluding secret keys and tokens).

Don’t hardcode sensitive settings, and don’t put them in VCS.

Split settings into groups: Django, third-party, project.

Follow naming conventions for custom (project) settings.

File Structure: 
```
project/
├── apps/
├── settings/
│   ├── __init__.py
│   ├── djano.py
│   ├── project.py
│   └── third_party.py
└── manage.py
```

settings.py:
 
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
settings_local.py:
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
Make sure to hide the SECRET KEYS

Set you environment in your Django Configuration file

## Questions
Why do there need to be so many different files that seem to be doing similiar things?
