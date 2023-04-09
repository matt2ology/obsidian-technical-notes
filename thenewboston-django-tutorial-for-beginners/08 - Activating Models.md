# Django Tutorial for Beginners - 8 - Activating Models

Week 14.5 | Friday, April 07, 2023 | 11:14 PM

related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [07 - Creating Models](07%20-%20Creating%20Models.md) - [Updating Django Database Model](Updating%20Django%20Database%20Model.md)

source : <https://youtu.be/dONYOtb2ySI>

## TL;DR

When ever you need to make a change to your database structure

1. Make the changes to your python code in the corresponding app's `models.py`
2. `python manage.py makemigrations app_name`
3. `python manage.py migrate`
 
When you make an app, after we make the template model, we need to go into project source folder into settings and place our app into `INSTALLED_APPS` section. This will allow the app to interop with the database correctly. `'music.apps.MusicConfig',` is added to the `INSTALLED_APPS` list.

Although we've defined our database models we still need to migrate the app's model to the actual database.

This makes the change file

```sh
python manage.py makemigrations app_name
```

> OR shows the tables and columns created to database
>
> > `python manage.py sqlmigrate app_name 0001`

Now we have to run the SQL (change) file

```powershell
python manage.py migrate
```

```txt
# Parent folder website - folder structure created
────website_project_folder
    │   db.sqlite3
    │   manage.py
    │
    ├───music                # python manage.py makemigrations music
    │   │   admin.py
    │   │   apps.py          # Reference this into settings.py
    │   │   models.py
    │   │   tests.py
    │   │   views.py
    │   │   __init__.py
    |   |   urls.py
    │   │
    │   └───migrations
    │           __init__.py
    │
    └───website
            asgi.py
            settings.py      # Update the `INSTALLED_APPS`
            urls.py
            request
            wsgi.py
            __init__.py
```

```python
# website\website\settings.py
INSTALLED_APPS = [
    'music.apps.MusicConfig',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```
