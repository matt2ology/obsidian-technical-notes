# Django Tutorial for Beginners - 2 - Creating a Project

Week 14.2 | Tuesday, April 04, 2023 | 02:26 AM

Source : https://youtu.be/CHjXtRrhqxc

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

![New Django Project Template File Explanation](New%20Django%20Project%20Template%20File%20Explanation.md)

![Django Comes with a Local Development Server](Django%20Comes%20with%20a%20Local%20Development%20Server.md)
