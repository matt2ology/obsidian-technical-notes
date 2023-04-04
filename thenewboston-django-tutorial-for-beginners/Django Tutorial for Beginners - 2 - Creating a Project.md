# Django Tutorial for Beginners - 2 - Creating a Project

Week 14.2 | Tuesday, April 04, 2023 | 02:26 AM

Related note : 

Initial start to creating a Django project - create the starter files

> django-admin startproject website

this will make a parent-folder and sub-folder "website" (or any name that you defined after `django-admin startproject`)

You can rename the root directory of the folder structure defined below
(root) website/website (sub-folder)

```txt
# $ django-admin startproject website
# Parent folder website - folder structure created
───website                # <- can rename parent-folder of the same name 
    │   manage.py
    │
    └───website           # <- this sub-folder must be left the same
            asgi.py
            settings.py
            urls.py
            wsgi.py
            __init__.py
```

### Explanation of each file in parent website, "project", folder

- manage.py
  - Don't touch, modify, or delete this folder
  - A program that allows you to access the database and create users for website
- website/asgi.py
- website/settings.py
  - Settings and configuration options for the entire-overall website
- website/urls.py
  - The URL declorations, the table of contents, for the website
  - `path('admin/', admin.site.urls)`
    - Look at whatever URL the user requested : `'admin/'`
    - Perform some functionality : admin.site.urls
- website/wsgi.py
  - Stands for Web-Server-Gateway-Interface (a special type of webserver)
- website/__init__.py
  - Is left blank to tell Python to treat it's foder as a package