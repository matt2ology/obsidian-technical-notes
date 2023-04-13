# Django Tutorial for Beginners - 11 - Admin Interface

Week 15.1 | Monday, April 10, 2023 | 11:24 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [Regular expression](../Regular%20expression.md)
Source : https://youtu.be/Mjs1elH3Pdg

Django already comes with an "admin" that affords one with special privileges, but before we can use it we must create it.

## Create Django Admin

This will create an administration of the backend (access to the database).

```term
python manage.py createsuperuser
```

If we wanted to have the means of editing the database of both the album and users table we can do so within the `music` app in the `admin.py`

We need to import the Python class/table and register the Python class/table model with the admin site so we can see it in the admin site.

Now we have the ability to Create - Read - Update - Delete items in our database.

![](_image-attachments/Pasted%20image%2020230410233153.png)
![](_image-attachments/Pasted%20image%2020230410233226.png)

```txt
# Parent folder website - folder structure created
────website_project_folder
    │   db.sqlite3
    │   manage.py
    │
    ├───music
    │   │   admin.py            # Where we can add tables for the admin
    │   │   apps.py
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
            settings.py
            urls.py
            request
            wsgi.py
            __init__.py
```

```python
# in website\music\admin.py
from django.contrib import admin

# we need this so we can register the Album model with the admin site
from .models import Album

# this is how we register the Album model with the admin site so we can see it in the admin site
admin.site.register(Album)
```
